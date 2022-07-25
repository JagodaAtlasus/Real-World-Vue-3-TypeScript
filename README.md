# real-world-vue

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Dokumentacja
https://vuejs.org/guide/typescript/composition-api.html
https://www.typescriptlang.org/docs/

## Tworzenie nowego projektu vue + typescript
 npm install -g @vue/cli -> vue create nazwa_projektu

## Dodanie typescript do istniejącego projektu
 vue add typescript 

## Zapis
 Dodajemy do skryptu "ts"
 <script lang="ts">
  
## Definiowanie typów - zapisujemy z małej litery po dwukropku po nazwie zmiennej

Number - let roomsize:number = 100;
String - let name:string = Kasia;
Tablica składająca się ze stringów - let shoppingList:string[] = ["woda", "cukier", "chleb"]
Funkcja - deklaracja typów na wejściu i wyjściu funkcji - 
let generateFullName = (firstName:string, lastName:string):string => {
return firstName + ' ' + lastName 
  }
Obiekt - definiowanie typów w obiekcie kończymy średnikiem -  
let person: {
    name:string;
    age:number;
    activeAvenger:boolean;
    powers:string[];
   } = {
    name: 'Peter',
    age:20,
    activeAvenger:true,
    powers:['wall crawl', 'spider-sense']
   }
  
## Customowe typy
 Jak zdefiniować kilka typów tego samego elementu - służy do tego type i interface
  type buttonType = 'primary' | 'secondary' | 'success'
  let buttonStyles:buttonType = 'secondary'
  
 type ComicUniverse = 'Marvel' | 'DC'
 interface Hero {
      name:string;
      age:number;
      activeAvenger:boolean;
      powers:string[];
      universe:ComicUniverse;
     }
  let person:Hero = {
      name:'Peter',
      age: 20,
      activeAvenger:true,
      powers:['wall crawl', 'spider-sense'],
      universe:'Marvel'
    }
  
## Dane z customowymi typami
 Type zapisujemy w osobnym pliku types.ts i eksportujemy.
 W komponencie importujemy dany typ i zapisujemy jako ={} as TodoItem.
  
## Type assertion
  np. interface TodoItem {
  label:string;
  completed:boolean;
  }
  const futureTodoItem = {} as TodoItem
  
## Customowe typy z propsami
  tzw. Generic - dynamiczne typy używane w funkcjach
  np. function createList<T>(item:T):T[]{
  const newList:T[]=[]
  newList.push(item)
  return newList
  }
  const numberList = createList<number>(123)
  const stringList = createList<string>('Hello')
