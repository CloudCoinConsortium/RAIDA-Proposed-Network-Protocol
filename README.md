# RAIDA-Proposed-Network-Protocol
This is a protocol that may be used in the future to communicate with the RAIDA


The proposed protocol will use UDP and not TCP

There will be several services that can be answered by the server. The first byte specifies the service that is being accessed:

00000000 Multi-Detect
00000001 Single-Detect
00000010 Multi-fix
00000011 Single-fix
00000100 Multi-Ticket
00000101 Single-Ticket


## Multi-Detect

After that, there are repeating fields of 36 bytes. 

1 Byte Network Number (N)
3 Bytes Serial Number (S)
1 Byte Instructions (I)
16 Bytes Authenticity Number (A)
16 Bytes Proposed Authenticty Number (P)

NSSSIAAAAAAAAAAAAAAAAPPPPPPPPPPPPPPPP


| 1 Byte  | 3 Byte | 1 Byte  | 16 Byte |16 Byte |
| ------------- | ------------- |------------- | ------------- |------------- |
| Network Number | Serial Number  | Instructions | Authenticity Number  | Proposed Authenticty Number |


Instructions:

00000000 Clear text, no special instructions
00000001 Encrypted using Public Key
 Every bit may have a different meaning. Now the rest are reserved for future use. 

There is no ending bytes. The server will calculate how many requests there are. 


