# monty41417

An elliptic curve over the prime field Fq(2^414-17) with cofactor h=4,
and twist cofactor h'=h. It has (perhaps) minimal values for Montgomery
form `A` and Bernstein-Lange-Edwards (`a=-1`) form `d0`. See 

No safety conditions from [SafeCurves][safecurves] yet verified besides
twist-security.

The curve parameters:

    A   = -2188290
    d_0 =   547073

The isogenous Edwards curve is:

    d = 18040a0e 99cb8dca 40c3a713 e40f5f74
        4e4d46ed ee6a66df a18723fc f4625e05
        239256a5 31b8e46d 69253a68 423835d4
        146d3933

[curve41417]: http://cr.yp.to/ecdh/curve41417-20140706.pdf "DJ Bernstein et al. Curve41417: Karatsuba revisited."
[safecurves]: http://safecurves.cr.yp.to/field.html
