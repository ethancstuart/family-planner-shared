# @family-planner/shared

## Overview
Shared TypeScript types, constants, and utility functions used by both the Family Planner web app (`family-planner-app`) and mobile app (`family-planner-mobile`).

## Package Design
- **No build step.** `"main": "src/index.ts"` points to raw TypeScript. Both Next.js (`transpilePackages`) and Metro (native TS support) transpile it directly.
- **Zero dependencies.** Only `devDependencies` for TypeScript. The `cn()` function (needs `clsx` + `tailwind-merge`) stays web-only.
- **`github:` dependency.** Both apps reference via `"@family-planner/shared": "github:ethancstuart/family-planner-shared"` — works both locally and in CI/Vercel/EAS. After editing the shared package, push to GitHub and run `npm install` in consumer apps to pick up changes.

## Exports
- `src/types.ts` — All shared TypeScript interfaces (Household, Recipe, MealPlan, GroceryList, etc.)
- `src/constants.ts` — DAYS_OF_WEEK, MEAL_TYPES, GROCERY_CATEGORIES, INGREDIENT_CATEGORY_MAP, getCategoryForIngredient()
- `src/utils.ts` — getWeekStartDate(), formatDate(), parseDate(), parseGroceryInput()
- `src/index.ts` — Barrel re-export of all above

## Consumers
- `family-planner-app` (Next.js web) — uses `transpilePackages` in next.config.ts
- `family-planner-mobile` (Expo/React Native) — uses `watchFolders` in metro.config.js

## Key Commands
- `npx tsc --noEmit` — type-check

## Conventions
- TypeScript strict mode
- Source of truth: this package. Do NOT duplicate types/constants/utils in consumer apps.
- When adding shared code, add to this package and both apps get it immediately.

## Shared Context — home-base
- `~/Projects/home-base/registry.md` — portfolio project registry
- `~/Projects/home-base/standards/quality.md` — shared quality standards
- `~/Projects/home-base/standards/design-principles.md` — shared design philosophy
