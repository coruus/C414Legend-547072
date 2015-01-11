# monty41417

An elliptic curve over the prime field Fq(2^414-17) with cofactor h=4,
and twist cofactor h'=h. It has (perhaps) minimal values for Montgomery
form `A` and Bernstein-Lange-Edwards (`a=-1`) form `d0`. See 

No safety conditions from [SafeCurves][safecurves] yet verified besides
twist-security.

The curve parameters:

    A   = -2188290
    d_0 =   547073

The trace of Frobenius:    

    3fffffff ffffffff ffffffff ffffffff
    ffffffff ffffffff ffff4dda 2f47fa6c
    6f1d641e 1ea9da59 70716f8a 6fb68977
    b7ccceab
    
Or, more conveniently:

    -286272342413254687855263543685952049463534566303544198955217220

## Isogenous complete Edwards curve

The corresponding Legendre curve has parameter `d=547073`; [Hamburg][hamburg]
notes the applicability of an isogeny derived in [Ahmadi & Granger][isogenies],
from which a complete Edwards (`a=1`) curve with small `d` may be derived.
(I still need to double-check I have the sign of that isogeny right...which
is why that parameter is not listed.)

## Verification

The curve was found by the method described in section 3.2 of [Bos et al.][nums].

The directory `traces/` contains, for each `A, A|4, -A<2188290`, either a small
factor of the order of the curve or its twist, formatted as,

    Vecsmall([1, {factor(q)|factor(q')}])
    
or a trace of the curve, with a partial factorization of the orders of the curve
and the twist

    [[0, [{isprime(q), isprime(q')]],
     [0, {trace(q)}],
     [[ {factor(order(q))} ], 
      [ {factor(order(q'))} ]
     ]
    ]

--

[hamburg]: http://eprint.iacr.org/2014/027 "Twisting Edwards curves with isogenies"
[isogenies]: https://eprint.iacr.org/2011/135 "O Ahmadi, R Granger. On isogeny classes of Edwards curves over finite fields."
[curve41417]: http://cr.yp.to/ecdh/curve41417-20140706.pdf "DJ Bernstein et al. Curve41417: Karatsuba revisited."
[safecurves]: http://safecurves.cr.yp.to/field.html
[nums]: http://eprint.iacr.org/2014/130/20140630:154727 "JW Bos et al. Selecting elliptic curves for cryptography."
