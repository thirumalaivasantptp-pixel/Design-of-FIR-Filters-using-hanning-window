# Design-of-FIR-Filters-using-hanning-window

#DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
clc;
clear;
close;
M = input("Enter the Odd Filter Length = ");        
Wc = input("Enter the Digital Cutoff Frequency (in radians) = ");  
alpha = (M - 1) / 2;    
for n = 1:M
    if (n == alpha + 1) then
        hd(n) = Wc / %pi;   
    else
        hd(n) = sin(Wc * ((n - 1) - alpha)) / (((n - 1) - alpha) * %pi);
    end
end
for n = 1:M
    W(n) = 0.5 - (0.5 * cos((2 * %pi * (n - 1)) / (M - 1)));
end
h = hd .* W;
disp(h, "Filter Coefficients are:");
[hzm, fr] = frmag(h, 256);  
subplot(2,1,1);
plot(2*fr, hzm);
xlabel("Normalized Digital Frequency (×π rad/sample)");
ylabel("Magnitude");
title("Frequency Response of FIR LPF using Hanning Window");
subplot(2,1,2);
hzm_dB = 20 * log10(hzm);
plot(2*fr, hzm_dB);
xlabel("Normalized Digital Frequency (×π rad/sample)");
ylabel("Magnitude (dB)");
title("Frequency Response of FIR LPF using Hanning Window (in dB)");
```
# OUTPUT
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/bfaf0512-3e5f-472a-b05f-4b68d0ff2798" />


# RESULT
Thus , generate design of low pass FIR digital filter using SCILAB are verified.
