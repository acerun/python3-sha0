# python3-sha0
Just for sha0 (others sha1, sha2... may use hashlib)

# Theory
SHA-0: A retronym applied to the original version of the 160-bit hash function published in 1993 under the name "SHA". It was withdrawn shortly after publication due to an undisclosed "significant flaw" and replaced by the slightly revised version SHA-1.

Changing source code for SHA-1 into one for SHA(-0) is easy: just remove the one-bit rotations of a 32-bit word of the 512-bit message block. For example, in the reference implementation of RFC 6234, change
```python
From:
w[i] = _left_rotate(w[i - 3] ^ w[i - 8] ^ w[i - 14] ^ w[i - 16], 1) #sha1
To:
w[i] = (w[i - 3] ^ w[i - 8] ^ w[i - 14] ^ w[i - 16]) #sha0
```

# Example
```python
sha0_v = sha0.sha0(b'1234')
```

# Reference
Thanks:
https://github.com/ajalt/python-sha1  
https://crypto.stackexchange.com/questions/62055/where-can-i-find-the-description-of-sha0-algorithm  
https://security.stackexchange.com/questions/183612/is-sha-synonymous-with-sha1-or-sha0