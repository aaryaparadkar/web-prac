## Typescript
### Calculator using TS
```
class Calculator {
    add(x: number, y: number) {
        return x + y
    }
    subtract(x: number, y: number) {
        return x - y
    }
    multiply(x: number, y: number) {
        return x * y
    }
    divide(x: number, y: number) {
        if (y == 0) {
            throw new Error("Cannot divide by 0")
        }
        return x / y
    }
}

const calculator = new Calculator()

console.log(calculator.add(5, 3))
console.log(calculator.subtract(5, 3))
console.log(calculator.multiply(5, 3))
console.log(calculator.divide(5, 3))
```

### Single level inheritance using TS
```
class Vehicle {
    brand: string

    constructor(brand: string) {
        this.brand = brand
    }

    drive(): void {
        console.log(`The ${this.brand} is being driven`)
    }
}

class Car extends Vehicle {
    model: string

    constructor(brand: string, model: string) {
        super(brand)
        this.model = model
    }

    honk(): void {
        console.log(`The ${this.brand} ${this.model} honks`)
    }
}

const car = new Car("Toyota", "Corrola")
car.drive()
car.honk()
```

### Multilevel Inheritance using TS
```
class Vehicle {
    brand: string

    constructor(brand: string) {
        this.brand = brand
    }

    drive(): void {
        console.log(`The ${this.brand} is being driven`)
    }
}

class Car extends Vehicle {
    model: string

    constructor(brand: string, model: string) {
        super(brand)
        this.model = model
    }

    honk(): void {
        console.log(`The ${this.brand} ${this.model} honks`)
    }
}

class ToyotaCar extends Car {
    color: string

    constructor(brand: string, model: string, color: string) {
        super(brand, model)
        this.color = color
    }

    design(): void {
        console.log(`The ${this.brand} ${this.model} is of ${this.color}`)
    }
}

const toyotacar = new ToyotaCar("Toyota", "Corrola", "Red")
toyotacar.drive()
toyotacar.honk()
toyotacar.design()
```

### Arrow Function in TS
```
const add = (a: number, b: number): number => {
    return a + b
}
```
