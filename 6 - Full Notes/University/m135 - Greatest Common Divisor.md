2025-08-15 11:15

Status:


Tags:
[[uni]] 
[[m135]] 


_______
# m135 - Greatest Common Divisor

Relates to → [[m135 - Divisibility of Integers|divisibility of integers]] 

**Definitions:** 
- **Common divisor:** an integer $c$ is a common divisor of $a$ and $b$ if $c|a$ and $c|b$ 
- **Greatest common divisor:** the largest number that divides both $a$ and $b$
	- $d=\text{gdc}(a, b)$ when:
		- $d$ is a CD of $a$ and $b$,
		- for all integers $c$ where $c$ is a CD of $a, b$, $c\leq d$ 
	- $\text{gcd}(0,0)=0$ 

**Propositions/Theorems:** 
- **Absolute value:** For all real numbers $x$, $x\leq |x|$ 
- **Bounds by divisibility (BBD):** For all integers $a, b$, if $b|a$ and $a\neq 0$ then $b\leq |a|$ 
- **Division algorithm (DA):** For all integers $a$ and positive integers $b$, there exist unique integers $q$ and $r$ such that $a=qb+r$ where $0\leq r<b$ 
	- $q$ → quotient
	- $r$ → remainder
- **GCD with remainders (GCD WR):** For all integers $a, b, q, r$ if $a=qb+r$ then $\gcd(a,b)=\gcd(b,r)$   
	- Useful for determining GCD efficiently (called **Euclidean Algorithm**)
		- I.e. $\gcd(1386,322)=\gcd(322,99)=\gcd(98,28)=\gcd(28,14)=\gcd(14,0)=14$ 
	- In other words → dividing $a$ by $b$ produces a new gcd with which you can compare with remainder
- **GCD characterization theorem (GCD CT):** For all integers $a,b$ and non-negative integers $d$, $d=\gcd(a,b)$ IF
	- $d$ is a common divisor of $a$ and $b$ and
	- there exists integers $s,t$ such that $as+bt=d$ 


**GCD properties:** 
- $\text{gcd}(a, a)=\text{gcd}(a, -a)=|a|$ 
- $\text{gcd}(a,1)=\text{gcd}(a,-1)=1$ 
- $\text{gcd}(a,0)=0$ 



# References

