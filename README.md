# SDd

This repository contains the implementation of SDd, a dynamic searchable symmetric encryption (DSSE) scheme proposed in [1]. SDd achieves forward and Type-II backward privacy [2], and it is one of the most efficient DSSE schemes with minimised storage cost on the client. Since this scheme is not implemented with an RPC framework, we integrate Apache Thrift with this scheme to evaluate its performance under the networked environment and compare it with the real network performance of a new DSSE scheme (Aura) proposed in our NDSS'21 paper [3].



## Requirements

* Git
* Ubuntu 18.04
* g++-7 (7.5.0 in ubuntu 18.04)
* cmake 3.17
* openssl 1.1.1
* Apache Thrift 0.13.0



## Building

```bash
git clone https://github.com/shangqimonash/SDd.git
cd SDd
mkdir build
cd build
# use cmake/make to build the code
cmake ..
make
```



## Usage

After compiling the project, three executable files of SDd will be generated. The first one is `SDdTest`, which runs SDd client and server operations as a local procedure. This can be used to evaluate the performance of Aura with no communication cost. The other two files (`SDdServer` and `SDdClient`)  can be used to execute Aura in a networked environment. Particularly, the `SDdServer` starts an Apache Thrift server which can process the setup, update, query operations from the `SDdClient`. The results from these two executable file reflect the performance of Aura in real-world networks.

All the above executable files can be executed without extra parameters.



## Feedback

- [Submit an issue](https://github.com/MonashCybersecurityLab/SDd/issues/new)
- Email the authors: shifeng.sun@monash.edu, shangqi.lai@monash.edu, xingliang.yuan@monash.edu



## Reference

[1] Ioannis Demertzis, Javad Ghareh Chamani, Dimitrios Papadopoulos, and Charalampos Papamanthou. 2020. Forward and Backward Private Searchable Encryption from Constrained Cryptographic Primitives. In *the Network and Distributed System Security Symposium* (*NDSS*). DOI: https://dx.doi.org/10.14722/ndss.2020.24423

[1] Raphaël Bost, Brice Minaud, and Olga Ohrimenko. 2017. Forward and Backward Private Searchable Encryption from Constrained Cryptographic Primitives. In *Proceedings of the 2017 ACM SIGSAC Conference on Computer and Communications Security* (*CCS '17*). Association for Computing Machinery, New York, NY, USA, 1465–1482. DOI: https://doi.org/10.1145/3133956.3133980

[3] Shi-Feng Sun, Ron Steinfeld, Shangqi Lai, Xingliang Yuan, Amin Sakzad, Joseph Liu, Surya Nepal, and Dawu Gu. 2021. Practical Non-Interactive Searchable Encryption with Forward and Backward Privacy. In *the Network and Distributed System Security Symposium* (*NDSS*). DOI: https://dx.doi.org/10.14722/ndss.2021.24162



