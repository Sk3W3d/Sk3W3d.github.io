## Well, see what this is. Python? 

> Nature isn't classical, dammit, and if you want to make a simulation of nature, you'd better make it quantum mechanical, and by golly it's a wonderful problem, because it doesn't look so easy. -- Richard Feynman

After getting help from the professor and TA (thanks a lot!), I finally implemented the Grover algorithm with QRAM. 

Technical details are boring but interesting :? Or I shall say: 

$$
\ket{\Psi} = \alpha\ket{easy}\otimes\ket{boring} + \beta\ket{difficult}\otimes\ket{intersting}
$$

Just some technical details for my own reference: 

QRAM = QRAM<sup>-1</sup>

Initialize $ \ket{address} $ into $ \ket{e<sub>1</sub>} $

Apply QRAM<sup>-1</sup> every time after calling the oracle. Originall, \ket{Address} and \ket{Data} are entangled. However, after applying the oracle, they are not. 