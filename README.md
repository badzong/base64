# base64
Simple public domain Base64 encoder and decoder with error checking.

Usage:

    #include <stdio.h>
    #include <base64.h>
  
    int main(void)
    {
        char *encode = "foobar";
        char *decode = "YmFyZm9v";
        char buffer[32];
        char *p;

        base64_encode(buffer, sizeof buffer, encode, strlen(encode));
        printf("encode: %s: %s\n", encode, buffer);
    
        p = base64_enc_malloc(encode, strlen(encode));
        printf("encode %s: %s\n", encode, p);
  
        base64_decode(buffer, sizeof buffer, decode);
        printf("decode: %s: %s\n", decode, buffer);
  
        p = base64_dec_malloc(decode);
        printf("decode %s: %s\n", decode, p);
  
        return 0;
    }
