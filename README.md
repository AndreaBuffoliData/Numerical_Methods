# 📊 Numerical Methods for Finance

Welcome to the **Numerical Methods for Finance** repository! 🚀  
This repository contains implementations of various **numerical methods** for financial applications, with a focus on **option pricing** using the **finite difference method**.

## 📖 Overview

This repository provides efficient implementations of numerical methods for pricing European options, including the **Crank-Nicolson finite difference method**. The goal is to provide accurate and stable solutions for financial derivatives where closed-form solutions (such as Black-Scholes) may not be applicable.

### ✨ Features:
- Implementation of the **Crank-Nicolson** method for European options.
- Supports **Call** and **Put** options.
- Generates **3D visualizations** of option prices over time.
- Well-structured, optimized, and efficient numerical approach.

---

## 📌 Finite Difference Method for Option Pricing

### 🔹 What is the Finite Difference Method?

The **finite difference method (FDM)** is a numerical technique used to solve differential equations. In finance, it is commonly applied to **option pricing** by discretizing the **Black-Scholes partial differential equation**. 

One of the best approaches within FDM is the **Crank-Nicolson method**, which provides a stable and accurate solution for European options.

---

## 🚀 How It Works

The function `finite_difference` implements the **Crank-Nicolson method** for pricing European options.  

### **📌 Parameters**
| Parameter | Description |
|-----------|-------------|
| `S` | Initial stock price |
| `K` | Strike price |
| `T` | Time to maturity (in years) |
| `sigma` | Volatility of the asset |
| `r` | Risk-free interest rate |
| `q` | Dividend yield |
| `N` | Number of time steps |
| `Nj` | Number of price partitions |
| `CallPut` | Option type: `'Call'` or `'Put'` |

### **📌 Example Usage**
```python
import numpy as np
import plotly.graph_objects as go
from finite_difference import finite_difference

# Define parameters
S, K, T, sigma, r, q, N, Nj = 100, 100, 1, 0.2, 0.05, 0.0, 100, 100

# Compute option price grid
grid = finite_difference(S, K, T, sigma, r, q, N, Nj, 'Call')

# Create 3D plot
X, Y = np.meshgrid(np.linspace(0, T, N+1), np.linspace(0, 2*K, 2*Nj+1))
Z = grid.T

fig = go.Figure(data=[go.Surface(z=Z, x=X, y=Y)])
fig.update_layout(title="Option Price Evolution - Crank-Nicolson",
                  scene=dict(xaxis_title="Time", yaxis_title="Underlying Price", zaxis_title="Option Value"))
fig.show()

```


## 🏗️ Project Structure

📂 numerical-methods 
│── 📄 finite_difference.py # Crank-Nicolson method implementation 
│── 📄 README.md # This documentation 
│── 📄 requirements.txt # Dependencies (if needed) 
│── 📄 examples.ipynb # Jupyter Notebook with examples and visualizations




---

## 📚 Academic References

If you're interested in the mathematical foundations of the Crank-Nicolson finite difference method and its applications in option pricing, here are some key academic references:

- **Black, F., & Scholes, M. (1973)** - *The Pricing of Options and Corporate Liabilities*, Journal of Political Economy.
- **Merton, R. C. (1973)** - *Theory of Rational Option Pricing*, Bell Journal of Economics and Management Science.
- **Brennan, M. J., & Schwartz, E. S. (1978)** - *Finite Difference Methods and Jump Processes Arising in the Pricing of Contingent Claims*, Journal of Financial and Quantitative Analysis.
- **Wilmott, P., Howison, S., & Dewynne, J. (1995)** - *The Mathematics of Financial Derivatives: A Student Introduction*, Cambridge University Press.
- **Crank, J., & Nicolson, P. (1947)** - *A Practical Method for Numerical Evaluation of Solutions of Partial Differential Equations of the Heat-Conduction Type*, Proceedings of the Cambridge Philosophical Society.

---

## 🤝 Contributing

Contributions are welcome! 🎉 If you'd like to contribute, follow these steps:

1. **Fork** the repository.
2. **Create a branch** for your feature (`git checkout -b feature-name`).
3. **Commit your changes** (`git commit -m 'Add new feature'`).
4. **Push to your branch** (`git push origin feature-name`).
5. **Open a Pull Request** and describe your changes.

Feel free to suggest improvements, report issues, or share ideas!

---

## 📜 License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute the code under the terms of this license.  
See the [LICENSE](LICENSE) file for full details.

---

## 🔗 Connect with Me!

If you have any questions, feel free to reach out or open an issue.  
Happy coding! 🚀📊
