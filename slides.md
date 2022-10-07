---
theme: geist
highlighter: shiki
title: Typescript základy
---

# Typescript ? 

- **Javascript** se syntaxí pro typy
- větší kontrola nad kodem
- lepší debugování - a docs přímo v IDE
- Valid JS code je valid ts = mužeme se učit inkrementálně

---


# Start 

```shell
npm i -g typescript // instaluje typescript globálně

tsc --version // verze ts
```

- Pro zájemce 🙋 [compiler options](https://www.typescriptlang.org/docs/handbook/compiler-options.html)


```shell
touch tsconfig.json // vytvoření configuračního jsonu
```
- Automaticky se přiřadí po spuštění
- Defaultní nastavení
```json
{
  "compilerOptions": {
    "target": "esnext"
  }
}
```
- Start
```shell
tsc index.ts
```
---


# Definování typů

## Implicitně 
- automaticky inferuje typy podle přiřazené hodnoty
```ts
let cislo = 13

cislo = "Ahoj" // Type error
```


## Explicitně 
- přímo určujeme typ
```ts
let cislo: number
cislo = "Ahoj" // Type error
```


---


# Nebo stackblitz
- typescript projekt

# Nebo typescript playground
- dobré pro zkoušení nových věcí v typescriptu a debug
- [https://www.typescriptlang.org/play](Playground)
---

## Typy 
- Primitivy `string`,`number`, a `boolean`
```ts
let cislo: number
let jeHotovo: boolean
let jmeno: string
```

## Array

- dva zápisy
```ts
let cisla: number[];

let texty: Array<string>;
```

---

## Tuples

- pro definování délky pole
```ts
let dveCisla: [string, number] = ["ahoj",0];

dveCisla[1] = 2;
```

## Any

- nespecifikujme typ - mužeme dělat co chceme - když nechcete psát typ

```ts
let obj: any = { x: 0 };


obj.foo();
obj();
obj.bar = 100;
obj = "hello";
const n: number = obj;
```
---

# Funkce
- parametr a return type
```ts
// Parametr type

function reverse(s: string) {
    return s.split("").reverse().join("");
}

reverse("hello world");

// Return type
function getFavoriteNumber(): number {
    return 26;
}
```

---

# Union types


```ts
let vysledek: number | string;
vysledek = [1] // type error

let jmeno: "Petr" | "Lukáš" | "Pavel" = "Pavel"
jmeno = "Test"
```

---

# Object types
```ts

const position = {
    x : 2,
    y : 3
}

function printPosition(position: { x: number; y: number }) {
  console.log("The position's x value is " + position.x);
  console.log("The position's y value is " + position.y);
}
```
