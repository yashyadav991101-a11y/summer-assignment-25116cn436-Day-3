# Day 3


## Q9. Check whether a number is prime

> **Logic:** *Check divisibility from 2 to sqrt(n). If any factor found, not prime.*

**C Code:**
```c
#include <stdio.h>

#include <math.h>

int main() {

    int n, prime = 1;

    printf("Enter number: ");

    scanf("%d", &n);

    if (n < 2) prime = 0;

    for (int i = 2; i <= sqrt(n) && prime; i++)

        if (n % i == 0) prime = 0;

    printf(prime ? "Prime\n" : "Not Prime\n");

    return 0;

}
```


## Q10. Print prime numbers in a range

> **Logic:** *Use a helper isPrime() function and iterate through the range.*

**C Code:**
```c
#include <stdio.h>

#include <math.h>

int isPrime(int n) {

    if (n < 2) return 0;

    for (int i = 2; i <= sqrt(n); i++)

        if (n % i == 0) return 0;

    return 1;

}

int main() {

    int a, b;

    printf("Enter range (a b): ");

    scanf("%d %d", &a, &b);

    for (int i = a; i <= b; i++)

        if (isPrime(i)) printf("%d ", i);

    printf("\n");

    return 0;

}
```


## Q11. Find GCD of two numbers

> **Logic:** *Euclidean algorithm: GCD(a, b) = GCD(b, a%b) until b becomes 0.*

**C Code:**
```c
#include <stdio.h>

int main() {

    int a, b;

    printf("Enter two numbers: ");

    scanf("%d %d", &a, &b);

    while (b != 0) { int t = b; b = a % b; a = t; }

    printf("GCD = %d\n", a);

    return 0;

}
```


## Q12. Find LCM of two numbers

> **Logic:** *LCM(a,b) = (a / GCD(a,b))  b. Divide first to avoid overflow.*

**C Code:**
```c
#include <stdio.h>

int gcd(int a, int b) { return b == 0 ? a : gcd(b, a % b); }

int main() {

    int a, b;

    printf("Enter two numbers: ");

    scanf("%d %d", &a, &b);

    printf("LCM = %d\n", (a / gcd(a, b)) * b);

    return 0;

}
```
