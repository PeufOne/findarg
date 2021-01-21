# findarg

En: Finds the value of the argument provides a function for a target result.

Fr: Trouve la valeur de l'argument fournit à une fonction pour un résultat cible.

> Does not work on chaotic functions

## Usage

```js
import findArg from 'findArg'

function myFunc(arg) {
    return arg**2
}

const targetResult = 9

const argument = findArg(myFunc, targetResult)

console.log(argument) // 3 ± 0.001

```

## Arguments

| Name         | Type     | Required | Definition                                  |
| :----------- | :------- | :------- | :------------------------------------------ |
| func         | Function | yes      | Function concerned                          |
| targetResult | Number   | yes      | Target result                               |
| options      | Object   | no       | Options to find the target argument faster. |

## Options

| Name          | type   | Default | Definition                                                                                       |
| :------------ | :----- | :------ | :----------------------------------------------------------------------------------------------- |
| keyResult     | String | null    | In the case where the function returns an object, this key allows to extract the targeted value. |
| currentArg    | Number | 0       | Argument whose result is known for the function.                                                 |
| currentResult | Number | 0       | Known result returned by the function with the aforementioned argument.                          |
| initialSlope  | Number | 1       | Slope of the function at the currentArg.                                                         |
| precision     | Number | 0.001   | Precision with which the target must be reached.                                                 |
| maxAttemps    | Number | 100     | Number of tries before abdicating.                                                               |
| isPerfLog     | Bolean | false   | Log the execution time of the resolution.                                                        |

## Return

Argument giving the target result.
If you provided the `keyResult` option, an object is returned :

```js
{
    argument: Number,
    result: {...} //<== Returned by your function
}
```

## Operation

TODO..