# 🔍 Hidden Pixels - Hidden Flag Extraction

## 🖼️ Given Image
The provided image was analyzed for hidden data using multiple steganography techniques. Initial methods such as **LSB extraction, raw binary analysis, and metadata inspection** yielded no results. 

## 🛠️ Analysis Process

### 🔎 1. Initial Steganographic Methods Attempted
- **LSB Extraction** (Least Significant Bit Steganography) ❌ No results
- **Raw Binary Data Search** ❌ No readable flag format found
- **Metadata Analysis** ❌ No hints or hidden text

Since these approaches failed, I moved on to more **advanced techniques**.

### 🖥️ 2. Bit-Plane Analysis with StegSolve
Using **StegSolve**, we examined individual bit planes to identify patterns or potential hidden messages. The following bit planes showed **interesting results**:

#### 🔄 Color Inversion (XOR Plane)
![Color Inversion](https://github.com/Friedlguana/PackAndShip/blob/hiddenPixels/Screenshot%202025-03-05%20230125.png?raw=true)
**Observation**: Some structured patterns emerged, but no clear flag detected.

#### 🟢 5th Bit of the Green Plane
![5th Bit Green](https://github.com/Friedlguana/PackAndShip/blob/hiddenPixels/Screenshot%202025-03-05%20230418.png?raw=true)
**Observation**: Faint outlines appeared, but no conclusive data.

#### 🔵 6th Bit of the Blue Plane
![6th Bit Blue](https://github.com/Friedlguana/PackAndShip/blob/hiddenPixels/Screenshot%202025-03-05%20230818.png?raw=true)
**Observation**: Some structured pixel patterns, possibly encoding information.

#### 🔹 Full Blue Plane (Best Detail!)
![Full Blue Plane](https://github.com/Friedlguana/PackAndShip/blob/hiddenPixels/Screenshot%202025-03-05%20230939.png?raw=true)
**Observation**: The most detailed bit-plane with distinct shapes. This plane was selected for further extraction.

#### 🔍 Extracted Data from the Blue Plane
![Extracted Data](https://github.com/Friedlguana/PackAndShip/blob/hiddenPixels/Screenshot%202025-03-05%20231157.png?raw=true)
**Observation**: No viable outputs were obtained. Further extraction methods may be needed.

## 🚧 Challenges Faced
Despite extracting the **blue plane**, we encountered issues:
- No clear **ASCII-readable** flag
- Possible **further encoding or transformation** applied
- Need for **advanced steganographic reversal techniques**

## 🏁 Conclusion
Although **conventional steganographic methods failed**, bit-plane analysis provided **key insights** into where the hidden data might be. The **blue channel** seems to contain the most detail, and further analysis is required to fully extract the flag.
