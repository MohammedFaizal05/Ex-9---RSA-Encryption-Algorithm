# RSA-Encryption-Algorithmm

## Aim:
 To Implement RSA Encryption Algorithm in C Program

 
## PROGRAM: 
```
#include <stdio.h>
#include <math.h>

int gcd(int a, int b) {
    while (b != 0) {
        int t = b;
        b = a % b;
        a = t;
    }
    return a;
}

long long mod_pow(long long base, long long exp, long long mod) {
    long long result = 1;
    base = base % mod;
    while (exp > 0) {
        if (exp % 2 == 1)
            result = (result * base) % mod;
        exp = exp >> 1;
        base = (base * base) % mod;
    }
    return result;
}

int main() {
    int p = 61;
    int q = 53;
    int n = p * q;
    int phi = (p - 1) * (q - 1);


    int e = 17; 
    int d = 0;
    for (int i = 1; i < phi; i++) {
        if ((e * i) % phi == 1) {
            d = i;
            break;
        }
    }

    int message;
    printf("Enter the message to encrypt (as a number): ");
    scanf("%d", &message);

    long long ciphertext = mod_pow(message, e, n);
    printf("Encrypted message: %lld\n", ciphertext);

    long long decrypted_message = mod_pow(ciphertext, d, n);
    printf("Decrypted message: %lld\n", decrypted_message);

    return 0;
}
```
## OUTPUT:
![Screenshot 2024-10-18 141321](https://github.com/user-attachments/assets/dca6285a-d306-41ff-a48b-cbf3721415cc)


## RESULT: 
Hence, Implement RSA Encryption Algorithm in C Program is done successfully.
