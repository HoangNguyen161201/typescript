# learn typescript:

> below is typescript code:

* interface:

```typescript
    interface Person {
        name: string
        age: number
    }

    const person: Person = {
        name: 'haongnguyen',
        age: 1
    }
```

* type:

```typescript
    type Name = string | 'hoang'

    const name: Name = 'hoang'
``` 

* type for class

```typescript
    interface UserClass {
        name: string;
    }

    class UserAccount {
        name: string;
        constructor(name: string) {
            this.name = name;
        }
    }

    const userClass: UserAccount = new UserAccount("nguyen quang hoang");

``` 

* set type for result password:

```typescript
    type User = {
        name: string
        age: number
    }
    const getAllUser = (): User=> {
        return {
            name: 'hoang nguyen quang',
            age: 18
        } 
    }
``` 

* type Union:

```typescript
   type name = 'hoang' | 'huy'
   type age = 1 | null | string []
``` 

* type array:

```typescript
    type StringArray = Array<string>;
    type NumberArray = number[];
```

* generic type:

```typescript
    interface User<T> {
        name: T
        age: number
    }
    const user: User<string> = {
        name: 'hoang',
        age: `
    }
```

* function generic:

```typescript
    type Func = <T>(a: T)=> T
    
    const active: Func = (a)=> a
    active('hoang')

    //
    function listPokemon<T>(a: T) {
        return a;
    }

    listPokemon<string[]>(["s", "b", "c", "f"]);
```

* giao lo:

```typescript
    interface Active1 {
        name: string
    }

    interface Active2 extends Active1 {
        age: number
    }

    type Active3 = Active2 & Active1 &{
        arms: boolean
    }
```

* readonly

```typescript
    interface User {
        name: string
    }

    const user = User {
        name: 'nguyen quang hoang'
    }

    usert.name= 'huynguyen' // false, can not fix name
```

* as const

```typescript
    const name = ['1','2','3'] as const // su dung khi chua khai bao kieu 
    name.push('hhh') // can not push value to array 
```

* ReadonlyArray: set array can't fix

```typescript
    const name ReadonlyArray<string>= ['1','2','3'] 
    name.push('hhh') // can not push value to array 

    const lastName: readonly string[]= ['1','2','3'] 
    lastName.push('hhh') // can not push value to array 

    const c = [1, 2, 3] as const;
    c.push("f");
```

* type Date

```typescript
    type TDate = Date;
    const date: TDate = Date.now();
    const date1: TDate = new Date();
```

* khai bao kieu tra ve

```typescript
    const getUser = (): string=> {
        return 'hoang nguyen'
    }
```

* khai bao kieu tuy chon

```typescript
    const getUser = (name?: string): string | undefined=> {
        return name
    }
```

* typeof

```typescript
    const getUser = (name?: string): string | undefined=> {
        if(typeof name == 'string') {
            return name
        }
    }

    const person = {
        name: string
    }

    type Person = typeof person & {
        age: number
    }

    type Pointer = {x: number}
    type P = keyof Pointer
``` 

* use ! to delete null and undefined

```typescript
    const name = (a: string | undefined) {
        return a!.toFixed()
    }
```

* any

* Type Aliases

```typescript
    type Point = { 
        name: string | undefined
        age: number
    }
```
* Type Aliases

```typescript
    const pokemon = 'ses' as string
```

*  Literal Types

```typescript
    const hoang4: 'hoang' = 'hoang'
```

*  use in: kien tra co key trong object hay khong

```typescript
    const person = {
        name: 'nguyen quang hoang'
    }
    function name(){
        if('name' in person) {
            console.log('nguyen quang hoang')
        }
    }
```

* type Function

```typescript
    const getPerson: Function = ()=> {
        return 'hoang'
    } 
```

* khai bao any bat ki bien gi

```typescript
    type person = {
        name: string
        [index: string]: any
    }
```

* khai bao type array moi

```typescript
    type Person = {
        [index: number]: string
    }

    const person: Person = ['fff', 'fffff']
```

* type array
```typescript
    type Gu = [string, number]
    const gu = [1, 'fdf', 'df', 2]
```

* cac kieu truy cap duoc lap chi muc
```typescript
    // get type theo chi muc
    type Person = {age: number}
    type Age1 = Person['age']

    // get type theo key
    const person = [
        {
            name: string
            age: number
        },
        {
            name: string
            age: number
            quang: string[]
        }
    ]
    type Person1 = typeof person[number]
```


// enums

```typescript
    enum Direction {
        up = 6, //6
        down, //7
        right, //8
        left //9
    }

    enum Direction1 {
        up, //0
        down, //1
        right, //2
        left //3
    }

    // enum string
    enum Direction2 {
        up= 'up',
        down= 'down',
        right= 's',
        left='f'
    }
```

  
* for of, for in, Một sự phân biệt khác là for..inhoạt động trên bất kỳ đối tượng nào; nó phục vụ như một cách để kiểm tra các thuộc tính trên đối tượng này. for..ofmặt khác, chủ yếu quan tâm đến giá trị của các đối tượng có thể lặp lại. Các đối tượng tích hợp như Mapvà Setthực hiện thuộc Symbol.iteratortính cho phép truy cập vào các giá trị được lưu trữ.

```typescript
    let list = [4, 5, 6];
    for (let i in list) {
        console.log(i); // "0", "1", "2",
    }
    for (let i of list) {
        console.log(i); // 4, 5, 6
    }
```

* any type
```typescript
    // Uppercase<T>
    type Gu1 = 'hoang ngyen'
    type Gu2 = Uppercase<'hoang ngyen'>
    type Gu3 = Uppercase<Gu1>

    //// Lowercase<T>
    type Gu4 = 'hoang ngyen'
    type Gu5 = Lowercase<'hoang ngyen'>
    type Gu6 = Lowercase<Gu4>

    // Capitalize<T>
    type Gu7 = 'hoang ngyen'
    type Gu8 = Capitalize<'hoang ngyen'>
    type Gu9 = Capitalize<Gu7>

    //Uncapitalize<T>
    type Gu10 = 'hoang ngyen'
    type Gu11 = Uncapitalize<'hoang ngyen'>
    type Gu12 = Uncapitalize<Gu10>

    // Partial: chuyen sang type co hoac khong
    const hoaa: Partial<{
    name: string
    }> = {
    name: 'fgfgf'
    }

    // nguoc lai voi partial
    const hoaa1: Required<{
    name: string
    }> = {
    name: 'fgfgf'
    }

    // Readonly<T>: chi duoc xen khong duoc sua
    interface Todo {
    title: string
    }

    const todo: Readonly<Todo> = {
    title: 'hoang gnuyen quang '
    }

    todo.title = 'dfsf'

    // Record : dat type cho cac string hay type khac nhu
    interface CatInfor {
        name: string
    }

    type CatName = 'hoang' | 'huy' | 'trong'
    const cart: Record<CatName, CatInfor> = {
        hoang: {
            name: 'd'
        },
        huy: {
            name: 'dddd'
        },
        trong: {
            name: 'dd'
        }
    }

    // Pick: lau chon cac field trong interface hay type
    interface Todo1 {
        name: string
        age: number
    }

    const todo1: Pick<Todo1, 'name'> = {
        name: 'goang '
    }

    // Omit nguoc lai voi todo1 la chon tat ca va loai bo 
    interface Todo2 {
        name: string
        age: number
    }

    const todo2: Omit<Todo2, 'age'> = {
        name: 'hoang'
    }

    //Exclude: laoi bo cac type union nhu
    type Todo3 = 'hoang' | 'huy' | 'trong'

    const todo3: Exclude<Todo3, 'hoang' | 'trong'> = 'huy'

    //Extract nguoc llai voi exclude
    type Todo4 = 'hoang' | 'huy' | 'trong'

    type Todo5 = Extract<Todo3, 'hoang' | 'trong'>

    // NonNullable: laoi bo null va undefined in type
    type Todo6 = string | null
    type Todo7 = NonNullable<Todo6>

    // ReturnType<type function> tra ve type cua func tra ve
    type T1 = ()=> string
    type T2 = ReturnType<T1>
```
