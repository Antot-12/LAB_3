# 🔐 Simple UDP Server with Encryption/Decryption

This repository contains a Python script that implements a basic UDP server. The server can receive messages from clients, broadcast them to all connected clients, and includes basic encryption and decryption functions.

## 📋 Features

- 🌐 **UDP Server**: Listens for incoming messages from clients and broadcasts them to all connected clients.
- 🔒 **Simple Encryption/Decryption**: Includes custom functions to encode and decode messages with a basic encryption algorithm.

## 🚀 Getting Started

### Prerequisites

- Python 3.x installed on your machine.

### 🛠️ Running the Server

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Antot-12/LAB_3.git
    cd LAB_3
    ```

2. **Run the server:**
    ```bash
    python server.py
    ```
   - The server will start and bind to the host's local IP address on port `4050`.
   - It will listen for incoming UDP packets from clients.

### 🛠️ Encryption and Decryption

The script includes basic encryption and decryption functions using a custom substitution method.

- **Encryption (`my_encode`)**: Shifts each letter in the string by a specified number of steps and adjusts numeric characters by a different step.
- **Decryption (`my_decode`)**: Reverses the encryption process, shifting letters and adjusting numeric characters back to their original values.

### ⚙️ Code Overview

#### Server Code

- **Initialization**: 
    - The server is initialized using the `socket` module, binding to the host's IP and port `4050`.
    - It maintains a list of connected clients.

- **Message Handling**:
    - The server listens for incoming messages.
    - When a message is received, it is printed to the console along with the sender's address and timestamp.
    - The message is then broadcasted to all connected clients, except the sender.

#### Encryption Functions

- **`crypt(in_str, step, step1)`**:
  - This function performs the actual encryption and decryption by shifting the alphabetic characters and adjusting numeric values.
  - The `step` parameter defines the shift for alphabetic characters, and `step1` defines the shift for numeric characters.

- **`my_encode(in_str)`**:
  - Uses `crypt` to encode a given string with a shift of `+2` for alphabetic characters and `+1` for numeric characters.

- **`my_decode(in_str)`**:
  - Uses `crypt` to decode a given string with a shift of `-2` for alphabetic characters and `-1` for numeric characters.

### 🛠 Usage Example

```python
# Example of encoding a message
encoded_message = my_encode("Hello World 123")
print(encoded_message)

# Example of decoding a message
decoded_message = my_decode(encoded_message)
print(decoded_message)
```

### 🐞 Troubleshooting

- **Server Not Responding**: Ensure that the correct port is open and not being used by another application.
- **Clients Not Receiving Messages**: Check network configurations and ensure all clients are correctly connected to the server.



---

Enjoy using the server and experimenting with encryption! 🔐
