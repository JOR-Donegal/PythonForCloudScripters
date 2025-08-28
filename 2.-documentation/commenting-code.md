# Commenting Code

I have seen an argument that properly written code is so self evident, it does not need comments. I do not agree! Sometimes when I write code, I do not revisit it for years and it can be a real struggle to remember what I did and why; the comments tell me why.

Below is an excerpt from a program I wrote for a company in 2021, who needed precision positioning for an autonomous vehicle. After some research, I understood the binary **domain specific language** (DSL) spoken by the navigation system, but there was nothing intuitive about it. I put a comment above almost every line to ensure the code was comprehensible to the company and that later I would also be able to understand what I did.

```
# Continuous loop until [ctrl][c]
        while True:
            # Read the first byte, if no byte, loop
            byte1 = Serial_Port1.read(1)
            if len(byte1) <1:
                break
            # Check for UBX header = xB5 and X62, Unicode = µb
            if byte1 == b"\xb5":
                byte2 = Serial_Port1.read(1)
                if len(byte2) < 1:
                    break
                if byte2 == b"\x62":
                    # Get the UBX class
                    byte3 = Serial_Port1.read(1)
                    # Get the UBX message
                    byte4 = Serial_Port1.read(1)
                    # Get the UBX payload length
                    byte5and6 = Serial_Port1.read(2)
                    # Calculate the length of the payload
                    length_of_payload = int.from_bytes(byte5and6, "little", signed=False)
                    # Read the buffer for the payload length
                    ubx_payload = Serial_Port1.read(length_of_payload)
                    # Last two bytes are 2*CRC, save them for later use
                    ubx_crc_a = Serial_Port1.read(1)
                    ubx_crc_b = Serial_Port1.read(1)
                    # Calculate CRC using CLASS + MESSAGE + LENGTH + PAYLOAD
                    payload_for_crc = byte3 + byte4 + byte5and6 + ubx_payload
                    # If the CRC is good, proceed
                    if ubx_crc(payload_for_crc,ubx_crc_a, ubx_crc_b):
                        # Log the ubx bytes
                        payload_for_save = byte1 + byte2 + payload_for_crc + ubx_crc_a + ubx_crc_b
                        with open (ubx_log_file, 'ab') as file:
                            file.write(payload_for_save)
```

There were other approaches I could have taken to coding this, perhaps using **enum**. Don't worry too much about understanding the code, consider the style of comments.

Based on PEP 8, comments should have a maximum length of 72 characters. If a comment is longer than this, use two or more lines.
