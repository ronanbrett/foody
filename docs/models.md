# Core Models

## Recipes

```ts
Recipe
{
    id: string,
    name: string,
    dateCreated: Date,
    dateUpdated: Date,
    createdBy: User.userId
    stages: [
        id: string,
        name: string;
        lanes: Step[]
    ],
    previousVersions: [string],
    servings: {
        defaultServing: 6
    }
}

Stage
{
    id: string;
    name: string;
    lanes: Step[]
}

Step
{
    id: string;
    instructions: Instruction[]
}

Instruction
{
    id: string;
    text: string;
    links: InstructionLink[]
    timing: Timing;
}

InstructionLink
{
    id: string;
    type: 'Equipment' | 'Technique' | 'Ingredient'
    linkId: string
    meta: 'EquipmentMeta' | 'TechniqueMeta' | 'IngredientMeta'
}

```

## Ingredients

```ts
Ingredient {
    id: string
    name: string
    img: string;
    unit: Unit
}

Unit {
    id: string;
    name: string;
    type: 'weight' | 'volume' | 'single'
}

IngredientMeta {
    id: string
    ingredientId: Ingredient.id;
    unitId: Unit.id;
    unitAmount: number;
}
```

## Technique

```ts
Technique {
    id: string
    name: string
    groupId: string;
    description: string;
    ingredientIds: string[]
}

```

## Equipment

```ts
Equipment {
    id: string
    name: string
    img: string;
    description: string;
}
```

## Measurements

## Plans

## User

# Linking Models

## Conversions (Graph Datastructure Map)
