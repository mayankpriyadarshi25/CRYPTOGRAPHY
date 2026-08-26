# Medical Image Encryption Using AES-256 and Chaotic Maps

A GUI-based medical image security application implementing hybrid encryption using AES-256 combined with chaotic systems (Logistic Map and Henon Map) for robust protection of sensitive medical images. Published research presented at **RACCAI 2026, 3rd International Conference, Chandigarh Group of Colleges University**.

## Research Paper

**Title:** A Hybrid Encryption Model for Medical Image Security in IoT Healthcare

**Published:** RACCAI 2026 — 3rd International Conference, CGC University

## Features

- **AES-256 Encryption** — military-grade cryptographic protection
- **Chaotic Key Generation** — Logistic Map and Henon Map for enhanced randomness
- **Full Encryption + Decryption** — complete encrypt/decrypt pipeline
- **Visual Output** — displays original, encrypted, and decrypted images side by side
- **Binary Export** — generates `.bin` file for secure encrypted image sharing
- **Image Quality Metrics** — SSIM (Structural Similarity Index) validation
- **Entropy Analysis** — statistical validation of encryption strength
- **GUI Interface** — easy-to-use Tkinter interface, no command line needed
- **SHA-256 Key Hashing** — secure key derivation from user input

## Tech Stack

- **Python** — core language
- **Tkinter** — GUI framework
- **PIL / Pillow** — image loading and processing
- **NumPy** — chaotic map computation and array operations
- **PyCryptodome** — AES-256 encryption and decryption
- **Hashlib** — SHA-256 key derivation
- **scikit-image** — SSIM image quality metrics
- **Matplotlib** — image visualization

## Encryption Algorithm

### How It Works

```
Input Image
    ↓
Flatten to 1D pixel array
    ↓
Generate 256-bit key via SHA-256 hashing
    ↓
Generate chaotic sequence using Logistic Map
    ↓
Permute pixels using Henon Map indices
    ↓
XOR scrambled pixels with AES-256 keystream
    ↓
Encrypted Image + .bin file output
```

### Chaotic Systems Used

**Logistic Map:**
```
x(n+1) = r * x(n) * (1 - x(n))
```
Used for pixel permutation index generation.

**Henon Map:**
```
x(n+1) = 1 - a*x(n)^2 + y(n)
y(n+1) = b*x(n)
```
Used for enhanced chaotic randomness in key stream generation.

## Installation

```bash
# Clone the repository
git clone https://github.com/mayankpriyadarshi25/medical-image-encryption.git

cd medical-image-encryption

# Install dependencies
pip install pillow numpy pycryptodome scikit-image
```

## How to Run

```bash
python main.py
```

The GUI will open automatically.

## Usage

**Encrypt:**
1. Click **Browse** to select a medical image
2. Enter encryption key
3. Click **Encrypt**
4. View encrypted image in GUI
5. Save `.bin` file for secure sharing

**Decrypt:**
1. Load the `.bin` encrypted file
2. Enter the same encryption key
3. Click **Decrypt**
4. View decrypted image — compared with original via SSIM score

## Security Features

| Feature | Implementation |
|---|---|
| Encryption | AES-256 CBC mode |
| Key Derivation | SHA-256 hashing |
| Pixel Scrambling | Logistic Map permutation |
| Chaos Enhancement | Henon Map |
| Padding | PKCS7 |
| Randomness | PyCryptodome secure random |

## Metrics & Validation

- **SSIM Score** — measures structural similarity between original and decrypted image (should be ~1.0 for perfect decryption)
- **Entropy Analysis** — validates randomness of encrypted output
- **Visual Inspection** — encrypted image appears as complete noise

## Use Cases

- Securing patient medical images (X-rays, MRIs, CT scans)
- IoT healthcare data protection
- Telemedicine secure image transfer
- Medical data compliance (HIPAA-aligned encryption)

## Research Contribution

This project demonstrates that combining AES-256 with chaotic systems provides stronger encryption than AES alone by:
- Increasing pixel randomness through chaotic permutation
- Making encrypted images statistically indistinguishable from noise
- Providing an additional layer of security against cryptanalysis attacks

## Author

**Mayank Priyadarshi**
- 💻 GitHub: [mayankpriyadarshi25](https://github.com/mayankpriyadarshi25)

## Disclaimer

This tool is developed for research and educational purposes in healthcare image security. Always follow applicable data protection regulations when handling real patient data.
