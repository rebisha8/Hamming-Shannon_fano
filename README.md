# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.
# Program:
```python
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
# Calculation:
![WhatsApp Image 2025-09-22 at 11 28 11_04cc2057](https://github.com/user-attachments/assets/c48e13ac-5aa2-4ec3-b6c6-1c73f86c8ec0)
![WhatsApp Image 2025-09-22 at 11 28 12_53986def](https://github.com/user-attachments/assets/b57a2d73-6072-4942-8aaa-afdf524f27d2)
![WhatsApp Image 2025-09-22 at 11 28 12_91935753](https://github.com/user-attachments/assets/9f6be27a-6608-4aa6-8744-f0b0d1f8773d)
![WhatsApp Image 2025-09-22 at 11 28 54_48a4427b](https://github.com/user-attachments/assets/c98a75cc-f94c-4332-b4e0-b2dfac969386)
![WhatsApp Image 2025-09-22 at 11 28 54_0ee29996](https://github.com/user-attachments/assets/4717e622-4c5f-4e39-bae3-4c3b371ad58e)

# Output
<img width="492" height="459" alt="image" src="https://github.com/user-attachments/assets/9b460974-20f2-4382-a121-b3e49cbcd3cf" />

# Results:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25 Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484.
