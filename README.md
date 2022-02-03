React Native Code Snippets

## Features

Extension to create React Native:

    - React Native Functional Component
    - React Native Functional Component & MobX Injection
    - MobX Store

## Requirements

React Native Functional Components have inherited react navigation interfaces. So make sure you have following react navigation setup.

    - ScreenProps.ts
    - RouteNames.ts
    - RouteProps.ts

#### ScreenProps.ts

ScreenProps interface file. Extends basic StackScreenProps which comes within react navigation.

```typescript
import { StackScreenProps } from "@react-navigation/stack";
import RouteNames from "./RouteNames";
import { RouteParams } from "./RouteParams";

export default interface IScreenProps<T extends RouteNames>
  extends StackScreenProps<RouteParams, T> {}
```

#### RouteNames.ts

Basic ScreenNames enum. Includes all react navigation screens' names.

```typescript
enum RouteNames {
  ScreenName1 = "ScreenName1",
}
export default RouteNames;
```

#### RouteParams.ts

Basic ScreenParams type. Includes all react navigation screens' params.

```typescript
import RouteNames from "./RouteNames";

type ValuableParams = {
  // ...
  [RouteNames.Screen1]: { param01: boolean };
  // ...
};

type DefaultParams = { [key in RouteNames]: {} | undefined };

export type RouteParams = DefaultParams & ValuableParams;
```
