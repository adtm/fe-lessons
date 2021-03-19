


## Komponentai

React'e viskas remiasi tais "komponentais" ir jie yra visko pamatas. Po apačia tai yra tas pats `html` ir `css` kurį tu rašai.

```javascript
// yra įvairių būdų kaip gali sukūrti komponentą
class Name extends React.Component {
    return (
        <div>"Hello"</div>
    )
}

function Name() {
    return "Hello"
}

const Name = () => "Hello"

// Visi jie truputį skiriasi, ir su laiku suprasi kodėl. Šiais laikais pagrinde naudojamas antras arba trečias variantas.
```

## Props

```javascript
// Čia matai, kad yra keiksmažodis "this", paprastai kalbant, kiekviena funkcija / klasė savo viduje turi priskirtus kintamuosius, ir klasėse jie pasiekiami su "this".
class Name extends React.Component {
    return (
        <div>{this.props.name}</div>
    )
}

function Name(props) {
    return props.name
}

// Jeigu atsimeni, aš dariau net tokią magiją kaip 
// .. = ({name}) => name
// tai vadinasi dekontravimu, jeigu objektas turi reikšmę obj = { name: ""}, tu gali paimti reikšmę kaip obj.name arba obj["name"] arba const {name} = obj (čia jis paima tą reikšmę)
const Name = (props) => props.name

// jeigu kažkas naudotų komponentą kaip
<Name name="John">
```

## Kombinavimas

```javascript
// minėjau, kad pagrindė idėja yra galvoti komponentais, mygtukas komponentas, kortelė, juosta, paieška, filtras, viskas yra komponentai.

// Kai turi keletą komponentų, gali juos pradėti kombinuoti, pvz
return (
    // čia vadinama fragmentu, kurie tingi div rašyti jį rašo
    <>
        <FullName />
        <LastName />
        // rodžiau, kad čia gali dar net JS rašyti
        { console.log("Hello") }
        { alert("Hello") }
        { names.map(name => (<FullName />))}
    </>
)
```