const operators = document.querySelectorAll(".operator")

operators.forEach((operator) => {
    operator.addEventListener("click", (event) => {
        lastValue = currentNumber.split('').pop()
        if (lastValue.includes('+') || lastValue.includes('-') || lastValue.includes('*') || lastValue.includes('/') || lastValue.includes('.') || lastValue.includes('%') && event.target.value === "%") {
            return
        } else {
            currentNumber += event.target.value
            updateScreen(currentNumber)
        }
    })
})

// business logic: equal-sign -> calculate

const equalSign = document.querySelector('.equal-sign')

equalSign.addEventListener('click', () => {
    calculatefromScreen()
})

const calculatefromScreen = () => {
    currentNumber = currentNumber.replace(/[^\d/*+x%()-.]/g, '')
    lastValue = currentNumber.split('').pop()
    if (lastValue.includes('+') || lastValue.includes('-') || lastValue.includes('*') || lastValue.includes('/') || lastValue.includes('.')) {
        return
    } else {
        currentNumber = currentNumber.replace(/x/g, "*")
        currentNumber = currentNumber.replace(/%/g, "/100")
        currentNumber = eval(currentNumber)
        updateScreen(currentNumber)
    }
}

// business logic: all-clear
const clearBtn = document.querySelector('.all-clear')

clearBtn.addEventListener('click', () => {
    clearAll()
    updateScreen(currentNumber)
})

const clearAll = () => {
    currentNumber = '0'
}

// business logic: backspace

const bsBtn = document.querySelector('.backspace')

bsBtn.addEventListener('click', () => {
    backSpace()
    updateScreen(currentNumber)
})

const backSpace = () => {
    if (currentNumber.length === 1 || typeof currentNumber === "number") {
        clearAll()
    } else {
        currentNumber = currentNumber.substring(0,currentNumber.length - 1)
    }
}

// business logic: main

const numbers = document.querySelectorAll(".number")

numbers.forEach((number) => {
    number.addEventListener("click", (event) => {
        inputNumber(event.target.value)
        updateScreen(currentNumber)
    })
})

let currentNumber = '0'

const inputNumber = (number) => {
    if (currentNumber === '0') {
        currentNumber = number
    } else if (typeof currentNumber === "number") {
        currentNumber = number
    } else {
        currentNumber += number
    }
}

const calculatorScreen = document.querySelector('.calculator-screen')

const updateScreen = (number) => {
    calculatorScreen.value = number
}

calculatorScreen.addEventListener("keyup", (event) => {
    if (event.key === 'Enter') {
        calculatefromScreen()
    } else {
        currentNumber = event.target.value
    }
})
