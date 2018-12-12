# Awesome-collisions ![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)
This repository contains a proof of concept for cryptographic functions that are vulnerable to `collision attack`   
I'm not a cryptography expert if you notice a mistake please open a issue  
If you have a PoC and want to be added send a pull request  
**The PoC and the research is not by me**  


# Functions table
| Function         | Is vulnerable | Added  |
|------------------|---------------|--------|
| MD4              | Yes           | Yes  	|
| MD5              | Yes           | Yes  	|
| SHA-1            | Yes           | Yes  	|
| SHA-2            | Theoretically | No     |
| SHA-3            | Theoretically | No     |
| RIPMED           | Yes           | No     |
| RIPEMD-128       | Yes           | No     |
| RIPEMD-160       | Yes           | No     |
| RIPEMD-320       | Yes           | No     |
| HAVAL-128        | Yes           | No    	|
| BLAKE-256        | NaN           | No     |
| BLAKE-512        | NaN           | No     |
| BLAKE2s          | NaN           | No     |
| BLAKE2b          | NaN           | No     |
| ECOH             | NaN           | No     |
| FSB              | NaN           | No     |
| GOST             | NaN           | No     |
| Grøstl           | NaN           | No     |
| HAS-160          | NaN           | No     |
| JH               | NaN           | No     |
| LSH              | NaN           | No     |
| MD2	             | NaN           | No     |
| MD6	             | NaN           | No     |
| RadioGatún       | NaN           | No     |
| SHA-224          | NaN           | No     |
| SHA-256          | NaN           | No     |
| SHA-384          | NaN           | No     |
| SHA-512          | NaN           | No     |
| Skein            | NaN           | No     |
| Snefru           | NaN           | No     |
| Spectral         | NaN           | No     |
| Streebog         | NaN           | No     |
| SWIFFT           | NaN           | No     |
| Tiger            | NaN           | No     |
| Whirlpool        | NaN           | No     |



&nbsp;
&nbsp;


## MD5  
#### Collision input (HEX Encoded)  
```
Input1: 4f64656420476f6c6472656963680a4f64656420476f6c6472656963680a4f64656420476f6c6472656963680a4f64656420476fd8050d0019bb9318924caa96dce35cb835b349e144e98c50c22cf461244a4064bf1afaecc5820d428ad38d6bec89a5ad51e29063dd79b16cf67c12978647f5af123de3acf844085cd025b956
Input2: 4e65616c204b6f626c69747a0a4e65616c204b6f626c69747a0a4e65616c204b6f626c69747a0a4e65616c204b6f626c69747a0a75b80e0035f3d2c909af1baddce35cb835b349e144e88c50c22cf461244a40e4bf1afaecc5820d428ad38d6bec89a5ad51e29063dd79b16cf6fc11978647f5af123de3acf84408dcd025b956
```
```php
md5("Input1") == md5("Input2")
```

&nbsp;


## MD4
#### Collision input (HEX Encoded)
```
Input1: a6af943ce36f0cf4adcb12bef7f0dc1f526dd914bd3da3cafde14467ab129e640b4c41819915cb43db752155ae4b895fc71b9b0d384d06ef3118bbc643ae6384
Input2: a6af943ce36f0c74adcb122ef7f0dc1f526dd914bd3da3cafde14467ab129e640b4c41819915cb43db752155ae4b895fc71b9a0d384d06ef3118bbc643ae6384
```
```php
md4("Input1") == md4("Input2")
```
&nbsp;


## SHA1
#### Collision input (HEX Encoded)
According to https://shattered.io
```
Input1: 255044462D312E330A25E2E3CFD30A0A0A312030206F626A0A3C3C2F57696474682032203020522F4865696768742033203020522F547970652034203020522F537562747970652035203020522F46696C7465722036203020522F436F6C6F7253706163652037203020522F4C656E6774682038203020522F42697473506572436F6D706F6E656E7420383E3E0A73747265616D0AFFD8FFFE00245348412D3120697320646561642121212121852FEC092339759C39B1A1C63C4C97E1FFFE017F46DC93A6B67E013B029AAA1DB2560B45CA67D688C7F84B8C4C791FE02B3DF614F86DB1690901C56B45C1530AFEDFB76038E972722FE7AD728F0E4904E046C230570FE9D41398ABE12EF5BC942BE33542A4802D98B5D70F2A332EC37FAC3514E74DDC0F2CC1A874CD0C78305A21566461309789606BD0BF3F98CDA8044629A1
Input2: 255044462D312E330A25E2E3CFD30A0A0A312030206F626A0A3C3C2F57696474682032203020522F4865696768742033203020522F547970652034203020522F537562747970652035203020522F46696C7465722036203020522F436F6C6F7253706163652037203020522F4C656E6774682038203020522F42697473506572436F6D706F6E656E7420383E3E0A73747265616D0AFFD8FFFE00245348412D3120697320646561642121212121852FEC092339759C39B1A1C63C4C97E1FFFE017346DC9166B67E118F029AB621B2560FF9CA67CCA8C7F85BA84C79030C2B3DE218F86DB3A90901D5DF45C14F26FEDFB3DC38E96AC22FE7BD728F0E45BCE046D23C570FEB141398BB552EF5A0A82BE331FEA48037B8B5D71F0E332EDF93AC3500EB4DDC0DECC1A864790C782C76215660DD309791D06BD0AF3F98CDA4BC4629B1
```
```php
sha1("input1") == sha1("input2")
```

&nbsp;

## PHP
```php
sha1('aaroZmOk') == sha1('aaK1STfY')
sha1('aaO8zKZF') == sha1('aa3OFF9m')
md5('240610708') == md5('QNKCDZO')
md5('aabg7XSs') == md5('aabC9RqS')
md5("0e215962017") == "0e215962017"
```
