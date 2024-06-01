# GPN CTF

#### Never Gonna Run Around and Reverse You

**Author: MisterPine**

**Category: Reversing**

**Description**

I thought of this really cool collision-free hash function and hashed the flag with it. Theoretically, you shouldn't be able to reverse it...

**Files**

* `never-gonna-run-around-and-reverse-you.tar.gz`
  * Inside the file:
    * `hash`
    * `hasher`

**Analysis**

The provided `hasher` program takes a flag as a command-line argument, performs a series of XOR operations on it, and prints the resulting hexadecimal string. The challenge is to reverse this process to retrieve the original flag.

**Steps to Reverse the XOR Process**

1. **Understand the XOR Logic:** The `main` function processes the input flag by:
   * Checking if the number of arguments is greater than 1.
   * Reading the input flag from `argv[1]`.
   * Computing the length of the flag.
   * Allocating memory for the flag plus two additional bytes.
   * Copying the flag into the allocated memory starting from the second byte.
   * XORing each byte of the flag (starting from the second byte) with the previous byte.
   * Printing the XOR-ed result in hexadecimal format.
2. **Reverse the XOR Process:** Given the hexadecimal hash, we need to convert it to bytes and reverse the XOR operation to retrieve the original flag.

**Python Code to Reverse the XOR Process:**

{% code overflow="wrap" fullWidth="false" %}
```python
def hex_to_bytes(hex_str):
    return bytes.fromhex(hex_str)

def reverse_xor_process(hex_bytes):
    original_bytes = [0] * len(hex_bytes)
    original_bytes[0] = hex_bytes[0]
    
    for i in range(1, len(hex_bytes)):
        original_bytes[i] = hex_bytes[i] ^ hex_bytes[i - 1]
    
    original_string = ''.join(chr(b) for b in original_bytes)
    return original_string

# The given hash
hex_string = "4717591a4e08732410215579264e7e0956320367384171045b28187402316e1a7243300f501946325a6a1f7810643b0a7e21566257083c63043404603f5763563e43"
hex_bytes = hex_to_bytes(hex_string)

# Find the flag
flag = reverse_xor_process(hex_bytes)
print("Flag:", flag)
```
{% endcode %}

**Result:**

{% hint style="success" %}
Flag: GPNCTF{W41t,\_h0w\_d1d\_y0u\_s0lv3\_th1s?\_I\_th0ught\_1t\_w45\_4\_g00d\_h45h}
{% endhint %}

