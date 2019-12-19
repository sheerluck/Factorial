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


