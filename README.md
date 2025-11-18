# RADAR_RANGE
# Evaluation of Radar Range Using Scilab
---

## AIM
To calculate the **maximum range of a radar system** using the **Radar Range Equation** and verify the results through **Scilab programming**.

---

## THEORY
The **Radar Range Equation** is a key relationship used in radar system design to determine the maximum distance (**range**) at which a radar can detect a target.  

It is expressed as:

<img width="965" height="329" alt="image" src="https://github.com/user-attachments/assets/d8d311e3-5625-4a58-966c-ca75dbb5109d" />

---

## ALGORITHM

1. Initialize constants:
   - λ (wavelength) = 0.03 m  
   - σ (radar cross section) = 1 m²  

2. Vary each parameter while keeping the others constant:
   - **Pt:** 0.1 → 10  
   - **Gt:** 1 → 50  
   - **Pm:** 1e⁻¹⁵ → 1e⁻¹⁰  

3. Compute maximum range using:
   R_max = ((Pt * Gt² * λ² * σ) / ((4π)³ * Pm))¼


4. Plot the following:
   - `Pt vs Rmax` 
   - `Gt vs Rmax` 
   - `Pm vs Rmax`
     
---

## PROCEDURE

1. **Refer to the Algorithm** and write the Scilab code for the experiment.  
2. **Open Scilab** on your system.  
3. **Create a New Editor File:**  
   - Go to `File → New → Script`.  
4. **Type Your Code** in the editor window.  
5. **Save the File** with a suitable name (e.g., `radar_range.sce`).  
6. **Execute the Code:**  
   - Press **F5** or click **Execute → File with echo**.  
7. **If Any Errors Occur:**  
   - Review and correct the code.  
   - Save and **run it again** until it executes successfully.

## PROGRAM
```scilab
c=3e8;
Gt=50;
Gr=50;
L=0.03;
sigma=10;
Pmin=1e-9;

Pt=0:0.05:5; 
R = (((Pt .* Gt .* Gr .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin)) ).^(1/4);
subplot(3,1,1);
plot(Pt,R);

G=0:0.05:5;

Pt=1;
R = (((Pt .* G .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin)) ).^(1/4);
subplot(3,1,2);
plot(G,R);

Gt=50;
Gr=50;
Pmin=1e-12:1e-12:1e-8;
R = (((Pt .* Gt .* Gr .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin)) ).^(1/4);
subplot(3,1,3);
plot(Pmin,R);
```


## OUTPUT

<img width="938" height="732" alt="image" src="https://github.com/user-attachments/assets/f9bf7e3f-70fa-4149-b312-d4b2ba948b0a" />


## CALCULATION

![WhatsApp Image 2025-11-18 at 21 14 57_7321e748](https://github.com/user-attachments/assets/4ac2dc7d-62dc-45c0-ac0e-e031839ab609)


## RESULT

Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.
