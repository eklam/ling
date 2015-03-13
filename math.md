class Calculator
  fibonacci:n
    if n
      < 0
        exception "n has to be grater than zero"
      <= 1
        return 1
      return fibonacci(n-1) + fibonacci(n-2)
        

class Math
  pow:n, base=2
    if base 
        <= 0
          exception
            "base has to be zero or greater"
        == 1 
          return n
        return n * pow(base-1)

