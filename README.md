11978571669969891796072783721689098706044844940833047813942754698563240738412203750719488000000000000

# 1) Python

```python
from math import factorial as f
f(70) - f(50)
```

# 2) Haskell

```haskell
let f n = product [1..n]
(f 70) - (f 50)
```

# 3) Julia

```julia
factorial(big(70)) - factorial(big(50))
```

# 4) Perl

```perl
use feature 'say';
use Math::BigInt;
use Math::BigInt lib => 'GMP';
say Math::BigInt->new('70')->bfac() - Math::BigInt->new('50')->bfac();
```

# 5) Golang

```go
package main

import (
    "fmt"
    "math/big"
)

func main() {
    var a big.Int
    var b big.Int
    var r big.Int
    a.MulRange(1, 70)
    b.MulRange(1, 50)
    r.Sub(&a, &b)
    fmt.Println(&r)
}
```

# 6) R

```r
install.packages("gmp", dependencies = TRUE)
gmp::factorialZ(70) - gmp::factorialZ(50)
```

# 7) C++

```cpp
#include <iostream>
#include <mp++/mp++.hpp>

using int_t = mppp::integer<1>;

int main()
{
    auto one = int_t{1};
    auto a = mppp::fac_ui(one, 70);
    auto b = mppp::fac_ui(one, 50);
    std::cout << a - b << '\n';
}
```

# 8) Scala

```scala
object Main extends App {
  def f(n: Int) = (BigInt(1) to BigInt(n)).product
  println(f(70) - f(50))
}
```

# 9) C#

```csharp
public static viod Main(string[] args) {
    Func<int, BigInteger> f = n => n < 2 ? BigInteger.One
              : Enumerable.Range(2, n-1)
                .AsParallel()
                .Aggregate(BigInteger.One, (acc, num) => acc * num);
    Console.WriteLine(f(70) - f(50));
}
```

# 10) Prolog

```prolog
n_factorial(0, 1).
n_factorial(N, F) :-
   N #> 0,
   N1 #= N - 1,
   n_factorial(N1, F1),
   F #= N * F1.

n_diff(C) :-
   n_factorial(70, A),
   n_factorial(50, B),
   C #= A - B.
```

# 11) Rust

```rust
use num::BigUint;
use num::One;

pub fn f(n: u64) -> BigUint {
  (1..=n).fold(BigUint::one(), |acc, num| acc * num)
}

fn main() {
  println!("f(70) - f(50) = {}", f(70) - f(50));
}
```

# 12) Nim

```nim
import bigints

func f(n: int): BigInt =
  result = 1.init_big_int
  for i in 2..n:
    result = result * int32(i)

echo f(70) - f(50)
```

# 13) Clojure

```clojure
(defn f [n] (reduce *' (range 1 (inc n))))
(- (f 70) (f 50))
```

# 14) Kotlin

```kotlin
import java.math.BigInteger
fun Int.toBig() = BigInteger(this.toString())
fun f(n: BigInteger): BigInteger {
    if (n == BigInteger.ONE) return BigInteger.ONE
    return n.multiply(f(n.minus(BigInteger.ONE)))
}
fun main() = println("f(70) - f(50) = ${f(70.toBig()) - f(50.toBig())}")
```

# 15) JavaScript

```javascript
function f(n) {
    if (n == 1n) return 1n
    return n * f(n - 1n)
}
f(70n) - f(50n)
```

# 16) Elixir

```elixir
defmodule F do
  def f(0), do: 1
  def f(n) when n > 0, do: Enum.reduce(1..n, 1, &*/2)
end
F.f(70) - F.f(50)
```

# 17) Coconut

```python
def f(0) = 1
addpattern
def f(n is int if n > 0) = range(1, n+1) |> reduce $ (*)
f(70) - f(50)
```

# 18) Crystal

```python
require "big"
def f(n)
  BigInt.new(n).factorial
end
print f("70") - f("50")
```

# 19) Guile

```guile
(define (f n) (if (zero? n) 1 (* n (f  (- n 1)))))
(- (f 70) (f 50))
```

# 20) Swift

```bash
$ git clone https://github.com/attaswift/BigInt.git
$ cd BigInt
$ swift run --repl
```

```swift
1> import BigInt
2> func f(_ n: Int) -> BigInt { (1 ... n).map { BigInt($0) }.reduce(BigInt(1), *) } 
3> print(f(70) - f(50))
```

# 21) Racket

```racket
(require math/number-theory)
(- (factorial 70) (factorial 50))
```
