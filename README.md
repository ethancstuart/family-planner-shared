# @family-planner/shared

Shared TypeScript types, constants, and utility functions for the Family Planner ecosystem.

## Usage

Referenced via GitHub in consumer apps:

```json
"@family-planner/shared": "github:ethancstuart/family-planner-shared#v1.0.0"
```

## Exports

- **Types** — Household, Recipe, MealPlan, GroceryList, TodoList, TodoItem, etc.
- **Constants** — DAYS_OF_WEEK, MEAL_TYPES, GROCERY_CATEGORIES, INGREDIENT_CATEGORY_MAP
- **Utils** — getWeekStartDate(), formatDate(), parseDate(), parseGroceryInput()

## Design

- No build step — raw TypeScript, transpiled by consumer bundlers
- Zero dependencies
- TypeScript strict mode

## Related Repos

- [family-planner-app](https://github.com/ethancstuart/family-planner-app) — Next.js web app
- [family-planner-mobile](https://github.com/ethancstuart/family-planner-mobile) — Expo/React Native iOS app

## License

MIT — see [LICENSE](LICENSE).
