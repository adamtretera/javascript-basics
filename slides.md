---
theme: geist
highlighter: shiki
title: Javascript základy
---

# Javascript základy
Vše potřebné pro vyvoj appky React ⚛️


---

# První script

- [ ] 🛠 Pro první testovaní budeme používat [Stackblitz](https://stackblitz.com/)
- [ ] Pokud nemáte **GitHub** založte si ho pod školním mailem 
- [ ] Dále budeme pracovat s IDE **WebStorm** (popř. VS code)
- [ ] Github education - [Jet brains licence](https://education.github.com/)


---
layout: image-right
class: bg-contain

image: ./images/fevsbe.jpeg

---

# Proč je JS super ? 

- **Client** - (webové aplikace) 💻
- **Server** - komunikace s databází 🗄
- Mobilní aplikace 📱
- Nespadne i když napište 💩 code

---

# Variables (Proměnná) - Boxíky 
- jsou kontejnery které uchovávají nějakou hodnotu
- místo v paměti počítače
- **Deklarace** = vytváření nové proměnné
- **Inicializace** = přiřazování hodnoty
```ts  
let jmeno; // Deklarace
jmeno = "Adam" // Incializace


let povolani = "Zametač frontendových krytin" // Incializace a deklarace
```

---

## const vs let vs var
- dříve `var` (dnes nepoužíváme) - scope ve funkci nebo globální

### const a let - block scoped {} 
- `let`
- `const` - signál pro javascript že se hodnota nebude měnit (toto neplatí pro Objekty a Array)


```ts 
const JMENO = "Adam"
JMENO = "Tomáš" // Inicializace error

let pozdrav = 'Ahoj!';
pozdrav = "Dobrý den!"

```
---

## Proč block scoped {}

```ts 
{
  let pozdrav = 'Ahoj';

  {
    console.log(pozdrav);
  }
}

console.log(pozdrav); // Error
``` 

---

## Hoisting

- interpreter alokuje paměť pro proměnné a deklarace funkcí (**rozdělení deklarace a inicializace**)
- `var = undefined ` - nehodí error
- `let` a `const` - nebudou vůbec inicializované


```ts  
console.log(test); // undefiend
var test; 
```
<div class="mt-5 flex justify-center">
<img class="rounded w-1/2" src="/images/hoisting.webp"/>
</div>




---

# Aritmetické operace 
`
let x = 3, y = 2
`


| Operace      | Název                        | Příklad           |
|--------------|------------------------------|-------------------|
| +            | Sčítání                      | `x + y = 5`       |
| -            | Odčítání                     | `x - y = 1`       |
| *            | Násobení                     | `x * y = 6`       |
| /            | Dělení                       | `x / y = 1`       |
| **%**        | Zbytek po dělení (**Modulo**) | `x % y = 1`       |
| ++           | Zvětšení o 1                 | `x++ // 4 `       |
| --           | Změnšení o 1                 | `x-- // 3`        |
| Math.sqrt()  | Odmocnina                    | `Math.sqrt(9) = 3` |
| **           | Mocenění                     | `2**3 = 8`        |


---

# Debugovaní

- Co se děje v kódu ?
- Preferujte konzoli
- `console.log(“Ahoj konzole”);`
- `debugger;` - spustí v devtools krokovací nástroj

```ts
// type
let vystupDoKonzole = "Ahoj svtěte!"

console.log(vystupDoKonzole);
alert(vystupDoKonzole)

```

### Devtools
- <KBD command option>C</KBD>
---

# Cvičení

- Nadeklarujte si dvě proměnné čísla (number).  a vypište do konzole rozdíl, součet, podíl, zbytek po dělení, násobení ?

---

# Primitives vs Objekty

- To co ukládáme do boxíků (proměnných)
- nejmenším stavebním kamenem v Javascriptu jsou právě primitivy
- vše, co není **primitiv**, je **objekt** (funkce, pole (array) , sety)
- Javascript auto wrapper (např. **String**) - vytvoří z primitvu `String.includes()`

- `string`
- `number`
- `bigint`
- `boolean`
- `undefined`
- `symbol`
- `null`
---

# Dynamic Weakly Typed
```ts 
let i = 17 
// nevím jestli je to int/string = dynamicky typované 
// dostane typ až za běhu (runtime)

``` 
- inferuje (převezme) typ podle hodnoty
- v tomtoo případě `number`

- **Grabage collection** =  automatické alokování paměti když se objekty vytváří a uvolňují když už nejsou používány

---

# Příklad 🧪
- runtime `typeof` funkce
- 💡 Protože je javascript weakly typed typy neurčujeme!


```ts 
typeof  23; // number
typeof "foo" // string
typeof null // null

typeof {} // Object
typeof [] // Object
typeof function() {} // Function (which inherits from Object)
```

---

# Práce se stringy  
- [String objekt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

```ts
"" ===  ''
"Ahoj světe".toLowerCase() === "ahoj světe"
"Ahoj světe".toUpperCase() === "AHOJ SVĚTE"
"Ahoj světe".charAt(1)   === "h" // "Ahoj světe"[1] === "h"
" Ahoj světe ".trim() === "Ahoj světe"
"Ahoj světe".includes("Ahoj") === true
"Ahoj světe".startsWith("Ahoj") === true
"Ahoj světe".endsWith("Ahoj") === false
"Ahoj světe".split(" ") === ["Ahoj", "světe"]
```

### Template literals - ``
```ts
let slovoCoChciVlozit = "Petr"
    
`string text ${slovoCoChciVlozit} string text`
```



---

# Matematické funkce
- objekt **Math**
- soubor různých funkcí a konstant
- [Math dokumentace](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
```ts
Math.random() // Vygeneruje náhodné číslo (0...1)
Math.round() // Zaokrouhluje číslo
Math.floor() // Zaokrouhluje číslo dolů
Math.ceil() // Zaokruhluje číslo nahorů

Math.PI // Pí
Math.E  // Eulerovo číslo

isNaN("ahoj") // true
123.toPrecision(2) // 12

```

- [Number objekt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

---

# Přetypování
- Z něčeho na string
```ts
(123).toString(); // "123"
true.toString(); // "true"

```

- Z čísla na string
```ts
parseInt("12") // 12
parseFloat("12.12") // 12.12
```
---

# Cvičení 🧪
- Dostanete větu  `" Typescript začal jako prototypovací scriptovací jazyk napsaný Brendanem Eichem v roce 1995 pro tehdejší Netscape browser pod názvem “Mocha”. "` 
- [ ] odstraňtě všechny mezery
- [ ] udělejte všechny písmena malá
- [ ] nahraďte slovo Typescript za Javascript
- [ ] zkontrolujte, zda začíná slovem Javascript a vypište to
- [ ] vypište celou zmodifikovanou větu

---

# Podmínky 
- Pokud platí logický výraz (**podmínka**), provede se daná část kódu
```ts
if (podmínka) {
    // nějaký kód
    console.log("podmínka je pravdivá")
} else {
    // nějaký kód
    console.log("podmínka je nepravdivá") 
}
```
- Co je ale taková podmínka ?
---

# Podmínka (Pravdivost)
- výraz co má hodnotu **truthy** nebo **falsy**
- pomocí `!` negace převedu na opačný výraz
- pomocí `!!` převedu hodnotu na `boolean` 
- např.
```ts
true; // true
!! "hello"; // true
!! -1; // true
!! []; // true
!! {}; // true

false; // false
!! null; // false
!! undefined; // false
!! 0; // false
!! ""; // false
```
---

# Porovnávání


| Operace | Příklad (true vyrazu) |
|---------|-----------------------|
| ==      | 2 == "2"              |
| ===     | 2 === 2               |
| !=      | 1 != "2"              |
| !==     | 1 !== 2               |
| >       | 2 > 1                 |
| >=      | 2 >= 2 , 2 >= 1       |
| <       | 1 < 2                 |
| <=      | 1 <= 2, 1 <= 1        |
| !       | !false                |

---


# Složitější podmínky

```ts
let username = "Petr Rychlý"

if (username === "Petr Pomalý") {
    // toto se neprovede
    console.log(`Jméno je ${username}`)
} else if (username === "Petr Rychlý") {
    // toto se provede
    console.log(`Jméno je ${username}`)
} else {
    // kdyby vše nevyšlo
    console.log(`Neznáme jméno`)
}

```

### Ternární operátor

```ts
let plnoletost = vek < 18 ? "neplnoletý" : "plnoletý"
```

---

# Switch
- nikdo nepoužívá :))
```ts
let operace = '+';

switch (operace) {
    case '+':
        vysledek = a + b;
        break;
    case '-':
        vysledek = a - b;
        break;
    default:
        console.error("neznáma operace");
}

```

---

# Logické operátory


- **a zároveň &&**
```ts
let drivingLicense = 'Super nový řidičák';
let age = 18;

if (drivingLicense && age >= 18) {
  console.log('Můžeš řídit auto!');
}

```

- **buď a nebo ||**
```ts
let level = 23;
let isPremiumAccount = true; 

if (level >= 10 || isPremiumAccount) {
  console.log('Můžeš jít do dungeonu!');
}
```
---


# Cykly
- jednoduchá cesta jak něco dělat **opakovaně**
- opakování nějaké akce několikrát

```ts
for (prvotníProměnná; podmínka; příkaz) {
    //  Nějaký kód
}
```
např.a
```ts
while (podmínka) {
    // Nějaký kód
    příkaz
}
```

---

# Příklad
```ts
for (let krok = 0; krok < 5; krok++) {
    // Běž 5 krát, od 0 až do 4 po 1
    console.log('Bežím jeden krok');
}
```
nebo
```ts
let početZboží = 0;
while (početZboží < 1) {
    console.log(`Máte pouze ${početZboží}`);
    početZboží++
}
```

---

## Příklad

- vypišete větu "Mám rád javascript po [**cisloIterace**]!" 8x
- vypište vaše jméno po zpátku 3x
