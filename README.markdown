# C414Legend-547072
## or HamburgPort, or MegaBikeshed

An elliptic curve over the prime field `Fq(2^414-17)` with cofactor `h=4`,
and twist cofactor `h'=h`. It has minimal values for Montgomery form `A`
and Bernstein-Lange-Edwards (`a=-1`) form `d0`.

Please call this isogeny class *C414Legend-547072*, and specify the map
used from the twisted BLE form. (You will likely want to actually use
the twist, which has positive trace, for which `d0=-547072`, as Robert
Ransom has pointed out.)

Many thanks to Robert Ransom for his help and advice. And many thanks
to Michael Hamburg for his useful patches to Pari. As Michael Hamburg
has pointed out, this curve was likely already [found][silent], but not
published, by Daniel Bernstein. Michael Hamburg also found this curve
earlier, but also did not publish it. (Private communication.)

The search technique used was that of [Bos et al.][nums].

So far as I know, Robert Ransom was the first to verify the safety
conditions.

The finite field parameter:

    q   = 2^414 - 17

The curve parameters:

    A   = -2188290
    d_0 =   547073

The trace of Frobenius:    

    t = -286272342413254687855263543685952049463534566303544198955217220

Or, in RFC-ish notation:

    q = 
    3fffffff ffffffff ffffffff ffffffff
    ffffffff ffffffff ffffffff ffffffff
    ffffffff ffffffff ffffffff ffffffff
    ffffffef

    trace = 
    3fffffff ffffffff ffffffff ffffffff
    ffffffff ffffffff ffff4dda 2f47fa6c
    6f1d641e 1ea9da59 70716f8a 6fb68977
    b7ccceab

## Isogenous complete Edwards curve

The corresponding Legendre curve has parameter `d=-547072`; [Hamburg][hamburg]
notes the applicability of an isogeny derived in [Ahmadi & Granger][isogenies],
from which a complete Edwards (`a=1`) curve with small `d` may be derived.

## Safety

(All credit for these calculations are due to Robert Ransom; any errors
are mine.)

The multiplicative embedding degree of the curve is (r - 1) / 1; the twist's
is (r' - 1) / 1.

```
((q + t + 1) / 4) - 1 ==
 2
 * 1454837227409
 * 3310275428377
 * 122080356233821987832370735873989797
 * 8995056468950086801855276752690557584641753054801154625370413833


(((q - t + 1) / 4 - 1) ==
2^2 * 3 * 67 * 193
 * 6532999441
 * 273696743558241429978400400999352161
 * 1245618882976002050792732102956988407
 * 30603945596507083378560724643797170349)
```

Discriminant of the endomorphism ring:

```
(t^2 - 4*q == 
 -1 * 2^2 * 17 * 41
 * 1535970058594945615559629891
 * 106726369147308716465204583067
 * 190967687917107147726500402369274104907639727523515978127004207763)
```

## Verification of minimality

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

## Next twist-secure curve: Legend-2188290

The curve with Montgomery form parameter

    A = -2188290

has trace

    -286272342413254687855263543685952049463534566303544198955217220

and thus `h=h'=4`.


[silent]: https://blog.silentcircle.com/this-one-goes-to-414/ "This one goes to 414"
[hamburg]: http://eprint.iacr.org/2014/027 "Twisting Edwards curves with isogenies"
[isogenies]: https://eprint.iacr.org/2011/135 "O Ahmadi, R Granger. On isogeny classes of Edwards curves over finite fields."
[curve41417]: http://cr.yp.to/ecdh/curve41417-20140706.pdf "DJ Bernstein et al. Curve41417: Karatsuba revisited."
[safecurves]: http://safecurves.cr.yp.to/field.html
[nums]: http://eprint.iacr.org/2014/130/20140630:154727 "JW Bos et al. Selecting elliptic curves for cryptography."
