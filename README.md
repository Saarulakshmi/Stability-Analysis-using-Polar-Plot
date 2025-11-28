# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/e361180f-4665-4412-8679-fa4d9b33c206" />
<img width="799" height="1280" alt="image" src="https://github.com/user-attachments/assets/71d1318a-4318-4611-a7b4-4fbbc068e40c" />


<img width="907" height="1280" alt="image" src="https://github.com/user-attachments/assets/54c0fb8d-df2f-4514-aa13-c27f2d7111cd" />

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
disp('stable')
elseif(Wpc == Wgc)
disp('marginally stable')
else
disp('unstable')
end
```
## Output:
<img width="413" height="307" alt="image" src="https://github.com/user-attachments/assets/45a77dfd-c324-425c-ba3a-1ee1b97af327" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7 <br>
Phase Margin =-8.88 <br>
Gain crossover frequency = 3.75 <br>
Phase crossover frequency = 3.16 <br>
The system is unstable
