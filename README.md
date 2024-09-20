Description
In 2015, in order to show the hugeness of the private key space (or maybe just for fun), someone created a "puzzle" where he chose keys in a certain smaller space and sent increasing amounts to each of those keys like this:

20 ≤ random key < 21 — 0.001 BTC
21 ≤ random key < 22 — 0.002 BTC
23 ≤ random key < 23 — 0.003 BTC
...
2255 ≤ random key < 2256 — 0.256 BTC
(total 32.896 BTC)

First #1–66 and #70, #75, #80, #85, #90, #95, #100, #105, #110, #115, #120, #125 private keys have already been cracked.

History
2015-01-15: a transaction was created containing a transfer transaction for 256 different Bitcoin addresses.

2017-07-11: funds from addresses #161—256 were moved to the same number of addresses of the lower range – thus increasing the amount of funds on them.

2019-05-31: the creator of the "puzzles" creates outgoing transactions with the value of 1000 satoshi for addresses #65, #70, #75, #80, #85, #90, #95, #100, #105, #110, #115, #120, #125, #130, #135, #140, #145, #150, #155, #160 with the aim of probably comparing the difficulty of finding a private key for the address from which such a transaction was carried out, and one that there is no transaction.

2023-04-16: somebody (maybe the owner) increased the unsolved puzzles prizes again by x10. Now the puzzle #66 prize is 6.6 BTC, #67 is 6.7 BTC and so on... puzzle #160 prize is 16 BTC.

2024-09-12: puzzle #66 (6.60126013 BTC) was solved by 1Jvv4yWkE9MhbuwGUoqFYzDjRVQHaLWuJd but the original spending transaction was replaced by bc1qpkp47q5cucrvnyepsdnjcv2kzyav5ze0ta7n67 spending only 5.93923605 BTC. Another address 15XVN6hFkzGdUTY1XcsYKXxRezjARwyBQx took the rest of the prize: 0.66100387 BTC.

Solution
Since every 5th puzzle has it's public key known, we can reduce the problem complexity from simple brute force to just solving the Elliptic Curve Discrete Logarithm Problem (ECDLP).
Brute forcing requires to iterate the whole range one by one, where on the ECDLP there exist algorithms that can solve the problem in about square root of operations of the key space. so for example, for puzzle 130, we only need to perform about the square root of 2^130 (which is about 2^65.5), and each operation is also much easier to compute than simple brute forcing, since we're only dealing with EC math and we don't need to generate the bitcoin addresses (which requires hashing the public key which is computationally expensive)
