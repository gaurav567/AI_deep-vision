<h3>Assignment 7A:</h3>

Check this paper out: https://arxiv.org/pdf/1409.4842.pdf (Links to an external site.)Links to an external site.
They mention on page 6, that the RF is 224x224. 
Use the formulas above and show the calculations

<br>Sol-:</br>

Layers | K | P | S | n_in | n_out=(n_in+2p-k)/s +1 | J_in | J_out=J_in * s | R_in | R_out=R_in +(K-1) * J_in
--- | --- | --- | --- |--- |--- |--- |--- |--- |---
Convolution | 7 | 2 | 2 | 224 | 112 | 1 | 2 | 1 | 1+(7-1)* 1=7
max_pool    | 3 | 0 | 2 | 112 | 56  | 2 | 4 | 7 | 7+(3-1)* 2=11
Convolution | 3 | 1 | 1 | 56 | 56   | 4 | 4 | 11 | 11+(3-1)* 4=19
max_pool    | 3 | 0 | 2 | 56 | 28   | 4 | 8 | 19 | 19+(3-1)* 4=27
Inception(3a) | 5 | 2 | 1 | 28 | 28 | 8 | 8 | 27 | 27+(5-1)* 8=59
Inception(3b) | 5 | 2 | 1 | 28 | 28 | 8 | 8 | 59 | 59+(5-1)* 8=91
max_pool      | 3 | 0 | 2 | 28 | 14 | 8 | 16 | 91 | 91+(3-1)* 8=123
Inception(4a) | 5 | 2 | 1 | 14 | 14 | 16 | 16 | 123 | 123+(5-1)* 16=187
Inception(4b) | 5 | 2 | 1 | 14 | 14 | 16 | 16 | 187 | 187+(5-1)* 16=251
Inception(4c) | 5 | 2 | 1 | 14 | 14 | 16 | 16 | 251 | 251+(5-1)* 16=351
Inception(4d) | 5 | 2 | 1 | 14 | 14 | 16 | 16 | 351 | 351+(5-1)* 16=379
Inception(4e) | 5 | 2 | 1 | 14 | 14 | 16 | 16 | 379 | 379+(5-1)* 16=443
max_pool      | 3 | 0 | 2 | 14 | 7  | 16 | 32 | 443 | 443+(3-1)* 16=475
Inception(5a) | 5 | 2 | 1 | 7 |  7  | 32 | 32 | 475 | 475+(7-1)* 32=603
Inception(5b) | 5 | 2 | 1 | 7 |  7  | 32 | 32 | 603 | 603+(7-1)* 32=731
avg pool      | 7 | 1 | 1 | 1 |  1  | 32 | 32 | 731 | 731+(7-1)* 32=923
