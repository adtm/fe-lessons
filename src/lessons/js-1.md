

## Kintamieji

JS yra trys būdai, kaip aprašomi kintamieji:
```javascript
// #1. Čia yra pats seniausias būdas, ir retai jau matomas gamtoje.
// (prasiplėsiu vėliau kodėl)
var name = "John";

// #2. Šitaip kūriami kintamieji, kai jų reikšmė keisis, pvz: vėliau norėsi pakeisti vardo reikšmę iš "John" į "Doe"
let name = "John";

// #3. Šitaip kūriami kintamieji, kai jų reikšmė nesikeis, t.y tu niekada negalėsi perrašyti jau egzistuojančios reikšmės. 
const name = "John"

// Išimtis yra su objektais, {}, jeigu reikšmė priskirta objektui, gali pakeisti viduje esančias reikšmes, pvz:
const name = { lastname: "", surname: "" }
name.lastname = "Doe" // čia yra validi operacija
```

> Takeaway: Stenkis visada naudoti `const`, kaip visur, yra skirtingų nuomonių, bet `const` užtikrina, kad reikšmė bus tokia kokia jos tikėjaisi.

## Kintamųjų reikšmių rūšys

JS yra daug įvairių tipų reikšmių, kurios gali būti priskirtos kintamąjam - nereikia to išmokti, viskas ateis su praktika. Išvardinu populiariausias, su daugiau nesu susidūręs.

```javascript
const name = "" // strings
const name = 1  // integers
const name = {} // objects
const name = [] // array (masyvas)
const name = new Name() // classes (klasės)

// jeigu eitume truputį giliau, galima priskirti funkciją kintamąjam, pvz:
const vardas = (name) => name

function vardas(name) {
    return name
}
// ^ abidvi funkcijos yra visiškai vienodos, pirmoji atsirado šiek tiek tik vėliau.

// ir iškviesti su
console.log(vardas("John"))
```

## (strings) kintamųjų rūšis
Nieko per daug čia nėra, tik yra vienas patogus niuansas.
````javascript
// Įsivaizduokime, kad yra užduotis: turėdama kintamajį vardas ir pavardė gražink pilną žmogaus vardą su pavardė. ("John" + "Doe" = "John Doe")
const name = "John"
const lastname = "Doe"

// paprasčiausias variantas
const fullname = name + " " + lastname

// truputį paprastenis variantas
const fullname = `${name} ${lastname}`

// kodėl antras naudojamas? Jeigu tau reikėtų sujungti daug kintamųjų, tai gražesnis ir paprastenis variantas.
````

> Gerai žinoti, kas "strings" yra kaip masyvo elementai, t.y: jei tau reikia pirmos raidės žodyje, užtenka padaryti `word[0]`.

Operacijas, kurias verta mokėti.
```javascript
const fullname = "John Doe"
// užduotis1: gražink "John Doe" tik pirmą žodį
fullname.split(" ") // gražins du masyvo elementus ["John", "Doe"]

fullname.length() // string ilgis
fullname.includes("John") // gražins ar kintamasis turi "John" 
fullname.slice(0, 4) // nuo 0 iki 4 imtinai gražins substring ("John")
```


## (array) kintamųjų rūšis
Pagrinde svarbu iteravimas ir kaip paimti konkretų elementą

```javascript
const arr = [1,2,3,4]

// iteruoti per elementus yra 2 būdai
for (item in arr) {
    console.log(item)
}
// ir
arr.map(item => console.log(item))
// antras yra paprastenis ir švarenis

arr.filter(item => item == 1) // gražins masyvą atfiltravus kurie yra lygūs 1
const [one,two] = arr // dar galima taip paimti pirmą ir antrą elementą

```