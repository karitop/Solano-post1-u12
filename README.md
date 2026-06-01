# Solano-post1-u12
## Laboratorio: Circuitos Cuánticos con Qiskit
**Arquitectura de Computadores — Unidad 12**

---

## Prerrequisitos
- Python 3.13+
- Qiskit 1.x: `pip install qiskit qiskit-aer matplotlib`

---

## Experimentos

### 1. Estado de Bell
Prepara el estado entrelazado |Φ⁺⟩ = (|00⟩ + |11⟩)/√2 aplicando una puerta Hadamard seguida de una CNOT.
<img width="575" height="269" alt="C1" src="https://github.com/user-attachments/assets/09642f9d-0008-4223-a4d6-d3e016c7849f" />


**Resultado esperado:** ~50% |00⟩ y ~50% |11⟩, nunca |01⟩ ni |10⟩.


| Estado | Conteo | Porcentaje |
|--------|--------|------------|
| \|00⟩  | 510    | 49.8%      |
| \|11⟩  | 514    | 50.2%      |

<img width="960" height="720" alt="bell_histogram" src="https://github.com/user-attachments/assets/1054d1e7-007b-4cc7-adf3-4f5e207bb475" />


---

### 2. Algoritmo de Deutsch-Jozsa
Determina si una función es constante o balanceada con una sola evaluación del oráculo. Clásicamente se necesitan hasta 3 evaluaciones para n=2.
<img width="610" height="93" alt="C2" src="https://github.com/user-attachments/assets/7e7e381c-22a5-411a-8dfc-4a887fda69bc" />

**¿Por qué 1 evaluación?** El algoritmo usa superposición e interferencia cuántica para evaluar la función en todos los inputs simultáneamente, colapsando el resultado a |00⟩ si es constante o a cualquier otro estado si es balanceada.

| Oráculo | Resultado | Interpretación |
|---------|-----------|----------------|
| Constante | {'00': 1024} | Función constante ✅ |
| Balanceada | {'11': 1024} | Función balanceada ✅ |

---

### 3. Algoritmo de Grover (2 qubits)
Busca un estado marcado en un espacio de 4 elementos con 1 iteración óptima.
<img width="544" height="366" alt="C3" src="https://github.com/user-attachments/assets/3cb9017e-4b4a-476f-bcc8-c743ca100dc4" />

**¿Por qué 1 iteración es suficiente para n=2?** Con 2 qubits hay 4 estados posibles. La fórmula del número óptimo de iteraciones es π/4 × √N, que para N=4 da exactamente 1.

| Target buscado | Estado encontrado | Probabilidad |
|----------------|-------------------|--------------|
| \|00⟩ | \|00⟩ | 100% ✅ |
| \|01⟩ | \|01⟩ | 100% ✅ |
| \|10⟩ | \|10⟩ | 100% ✅ |
| \|11⟩ | \|11⟩ | 100% ✅ |
<img width="960" height="720" alt="grover_00" src="https://github.com/user-attachments/assets/c4e889f3-53e0-4110-b618-a7b8589e04d4" />
<img width="960" height="720" alt="grover_01" src="https://github.com/user-attachments/assets/526daf23-eb28-4cc8-a7f9-bc1c40deb718" />
<img width="960" height="720" alt="grover_10" src="https://github.com/user-attachments/assets/a0135264-7f89-4e0b-9de8-8016b19a2395" />
<img width="960" height="720" alt="grover_11" src="https://github.com/user-attachments/assets/cc847297-d50e-4c7e-98df-753e4137a952" />

---
