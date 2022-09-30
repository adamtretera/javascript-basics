---
theme: geist
highlighter: shiki
title: Javascript základy
---

# Javascript základy
Vše potřebné pro vyvoj appky v Reactu ⚛️


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

# Klíčové slova - const vs let vs var
- dříve `var` (dnes nepoužíváme) - scope ve funkci nebo globální
## Co se používá ? - (block scoped) 
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

## Komentáře
- Proč ? Vysvětlení kódu pro tebe v budoucnosti nebo ostaní developery.
- inline pomocí `// Komentář na řádek`
- blokový pomocí `/* Komentář na celý blok kódu */`
```ts
let x = 5;      // Deklarace x a inicializace x s hodnotou 5 (vytvoření a uložení hodnoty 5)
/*
  např. Tuhle hodnotu neměnit, může způsobit problémi v souboru index.html
  const IMPORTANT_NUMBER = 5;
  raději změnte vytvořte novou proměnnou
*/
const IMPORTANT_NUMBER = 5;

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
- Javascript auto wrapper (např. **String**) - vytvoří z primitvu Objekt `String.includes()`

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

# String objekt
- [MDN - refrence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

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
!!"hello"; // true
!!-1; // true
!![]; // true
!!{}; // true

false; // false
!!null; // false
!!undefined; // false
!!0; // false
!!""; // false
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
// Přihlášení

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
    // v případě že operace je "+"
    case '+':
        vysledek = a + b;
        break;
    // v případě že operace je "-"    
    case '-':
        vysledek = a - b;
        break;
    // defaultní hodnota stane se pokdu žádna podmínka nebyla splněna
    default:
        console.error("neznáma operace");
}

```


---

# Cvičení 🧪

- předělejte kalkulačku která podle operace (+, -, %, *, /) provede danou operaci
- na konci vypište zda výsledné číslo je negativní (menší než nula) - použijte ternární operátor


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
- **iterace** - průchod cyklem (1 iterace = 1 průchod)

```ts
for (prvotníProměnná; podmínka; příkaz) {
    //  Nějaký kód
}
```
např.
```ts
while (podmínka) {
    // Nějaký kód
    příkaz
}
```

---

# Příklad -  for

- opakuje se do té doby dokud není splěna nějaká podmínka
vytvořený pomocí 3 výrazů 
- <span class="text-blue-500 font-bold">inicializace</span>
(např. let i = 0), <span class="text-red-500 font-bold">podmínky</span> (např. i < 9), <span class="text-green-500 font-bold">akce po interaci</span> (např. i++)
- for(<span class="text-blue-500 font-bold">let i = 0</span>; <span class="text-red-500 font-bold">i < 9</span>; <span class="text-green-500 font-bold">i++</span>)

```ts
for (let krok = 0; krok < 5; krok++) { 
    // Běž 5 krát, od 0 až do 4 po 1
    console.log('Bežím jeden krok');
}

let jmeno = 'adam';

for (let i = 0; i < jmeno.length; i++) {
    // jedná se o blok mužeme vkládat libovolný kod např. podmíku
    if (i === 0) {
        // pokud se jedná o první interaci (první písmenko)
        console.log(jmeno[i].toUpperCase()); // vypíšeme velkým znak na pozici i
    } else {
        console.log(jmeno[i]); // vypíšeme znak na pozici i
    }
}

```
---

# Příklad -  while

```ts
let početZboží = 0;
while (početZboží < 1) { // zkontroluju podmínku a teprve poté pokračuji
    console.log(`Máte pouze ${početZboží}`);
    početZboží++
}

let rokVzniku;
do {
    // něco udělám alespoň jednou
    rokVzniku = prompt("Zadejte rok vzinku JavaScriptu ?");
} while (rokVzniku !== "1995") // až nyní zkontroluju podmínku

// Infnite loop (nebude fungovat) - JS crashne
while (true) {
    console.log('Hello, world!');
}


```

---

## Příklad

- vypišete větu "Mám rád javascript po [**cisloIterace**]!" 8x
- vypište vaše jméno po zpátku 3x

---

# Array - pole []
- pro ukládání více hodnot pod jednu proměnnou
- k hodnotám v poli jsou přiřazeny pozice (**indexy**) od 0
<Array/>


```ts

const nakup = ['chleba', 'mléko', 'sýr', 'nudle', 'káva'];
console.log(nakup);

```


---

# Práce s Arrays (1/2)

```ts
const nakup = ['chleba', 'mléko', 'sýr', 'nudle', 'káva'];
```

- **Délka pole** `length`
```ts 
console.log(nakup.length);  // 5
```
- **Přístup pomocí indexu (pozice)** 
- 
```ts
nakup[0] = 'rohlik'; // console.log(nakup)  ['rohlik', 'mleko', ...]
```

- **Najít hodnotu** vrací pozici (index) `indexOf()`

```ts
nakup.indexOf("sýr") // 2
```

- **Převrácení pořadí**  `reverse()`

```ts
nakup.reverse() // ["káva", "nudle", "sýr", "mléko", "chleba"]
```

---

# Práce s Arrays (2/2)
- **Přidávání hodnot** `push()` a `unshift()`

```ts
nakup.push("šunka")  // přidá na konec 
nakup.unshift("čaj")  // přidá na začátek
```

- **Odebírání hodnot** `pop()` a `shift()`

```ts
nakup.pop()  // odebere od konce
nakup.shift()  // odebere od začátku
```

- **Další...**
```ts
[1,2].concat([3,4])  // [1,2,3,4]
['Adam', 'Tretera'].join()  //  Adam,  Tretera
```
---

# Procházení pole

- pomocí cyklů :))

```ts
const zoo = ['žirafa', 'pes', 'opice', 'zebra', 'lev'];

for (let i = 0; i < zoo.length; i++) {
  console.log(zoo[i]);
}
```

---

# Procházení pole 

```ts
const zoo = ['žirafa', 'pes', 'opice', 'zebra', 'lev'];

for (const zvire of zoo) {
  console.log(zoo.indexOf(zvire)); 
}

for (const zvireIndex in zoo) {
  console.log(zvireIndex);
}
```
---

# Cvičení 🧪
1. [3, 5, 7, 8, 11, 12, 13, 16, 17, 18] vypište všechna sudá čísla
2. Dostanete na vstupu **vaše jméno** ("Adam Tretera") a musíte vypsat iniciály, křestí jméno a příjmení


---


# Funkce
- pro rozdělní velkých kusu kodu do malých částí
- **parametr** je při deklaraci funkce
- **argument** je při volání funkce bread
- return defaultně undefined ⇒ ale můžeme nahradit vlastním při použití `return` statementu
- **hoisted** - můžu přistoupi před deklarací
  <img class="rounded w-1/2 mt-3" src="/images/img.png"/>



---

# Funkce

```ts
// vytvořím funkci s názvem makeLunch
function makeLunch() { 
    console.log("🍕") // vypíšu do konzole "🍕"
    return "🍕" // vracím z funkce "🍕"
}

makeLunch();  // 🍕
makeLunch();  // 🍕
makeLunch()  // 🍕

let pizza = makeLunch() // přiřazuju emoji k proměnné pizza
```
---

# Funkce
```ts
// vytvořím funkci reverseName s paremetrem name
function reverseName(name) {
    // uložím si do proměnné obracené jméno
    const result = name.split('').reverse().join('');
    // vracím výsledek
    return result
}
// tady si uložím výsledek který funkce vrátím při poskytnutí argumentu "tonda"
let tondaReversed = reverseName("tonda")


function findIndex(array, element) {
    for (let i = 0; i <= array.length; i++) {
        if (element === array[i]) {
            return i;
        }
    }
}

console.log(findIndex([1, 2, 8, 9], 2)); // 1 (vracím index kde jsem našel hodnotu)



```

---

# Cvičení (co nestihnete je na doma)
1. Vytvořte funkci, která převede minuty na sekundy 
```ts
minToSec(3) // vrátí 180
minToSec(2) // vrátí 60
```
2. Funkci, která bere dva paremery boolean a vrací hondotu true jen v případě že oba parametry byly také true
```ts
aZaroven(true, true) // true
aZaroven(false, true) // false
```
3. Vytvoř funkci, která bere dva paremetry např. (x,y) a vrací obsah, pokud jsou zadané špatné argumenty vratí -1
---

# Objekty

- Objekt  je kolekce vlastností
- **Property** (vlastnost) je dvojice klíč-hodnota (key - value), která obsahuje název a hodnotu. => proměnná přiřazená k objektu
- **Property Name** (name)
- **Property Value** může být jakákoli hodnota, včetně jiných objektů nebo funkcí
```ts

typeof {} // object
typeof [] // object

const obj = {} // literal syntax
obj = new Object() // constructor syntax 

```
---

# Objekty základy
- funkce na objektu je methoda
```ts
const user = {
    name: 'Adam',
    lastname: 'Tretera',
    id: 88799779,
    parents: [919233, 12323123],
    childrens: [],
    job: function createApp() {
        return 'Nová appka';
    },
    imageUrl: 'google.com',
};

```
---

# Objekty základy - práce

```ts
const clone2 = { ...user };

console.log(clone === user); // false

user.id = 123;

const sugar = { ...original, hola: 'mundo' };

const { name, lastaname } = user;

const users = [
    {name: "Adam", id: "13"},
    {name: "Petr", id: "15"},
    {name: "Petr", id: "19"}
]

```


---

# Function expression
- **Anonymní funkce** - funkce bez jména
```ts
// Anonymní funkce
(function() {
    console.log("🍕")
    return "🍕"
})
```

- **Function expression**
- můžeme přiřadit anonymní nebo jinou funkci k proměnné
- není hoistované

```ts
const makeLunch = function() {
	console.log("🍕")
	return "🍕"
}
```


---

# Arrow funkce ➡️
- jednoduší zápis funkce
- Proč ? vkládám funkci jako argument jiné funkci 
```ts
(paremetr) => {
  // výraz
  return parametr + 100;
};
```


```ts
const makeLunch = () => {
	return "🍕"
}
```
---

# Methody na Array
- berou jako paremtr funkce vetšinou používáme anonymní () => {} arrow funkce
- vše najdete zde [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) 



```ts
const zoo = ['🦁', '🐵', '🐼', '🐝', '🐨'];


zoo.forEach((animal) => console.log(animal)); // co se má stát pro každý item (vrací undefined)
const zviratka_s_trickem = zoo.map((item) => item + '👕'); // vrací novou array
const jenomPandy = zoo.filter((item) => item === '🐼'); // vrací novou array
const majiTricka = zoo.every((item) => item.includes('👕')); // false  (platí pro všechny ?)
const indexOpice = zoo.find((item) => item === '🐵'); // 1 //vratí první vyhovující
```


---

# Bonus

