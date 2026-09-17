# FIR-FILTER-DESIGN
# EXP 4 b: Design-of-FIR-Digital-Filter-using-Hanning-Window

# AIM 1:

To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

# APPARATUS REQUIRED: 

PC installed with SCILAB. 

# PROGRAM: 
clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) = Wc/ %pi ;

else

hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);

end

end

// hanning Window

for n = 1:M

W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR LPF using Hanning Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR LPF using Hanning Window');

# OUTPUT: 

<img width="848" height="635" alt="image" src="https://github.com/user-attachments/assets/d76decde-b2fc-438a-8719-8918333901a0" />


# RESULT: 

Thus design of low pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) = 1-Wc/ %pi ;

else

hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);

end

end

for n = 1:M

W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR HPF using Hanning Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR HPF using Hanning Window');



# OUTPUT: 
<img width="913" height="659" alt="image" src="https://github.com/user-attachments/assets/63295f25-072b-452e-a38f-3d062357b160" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

Wc2=Wc(2);

Wc1=Wc(1);

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) =(Wc2-Wc1)/%pi ;

else

hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);

end

end

//Hanning Window

for n = 1:M

W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));


end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR BPF using Hanning Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR BPF using Hanning Window');

# OUTPUT: 

<img width="897" height="607" alt="image" src="https://github.com/user-attachments/assets/fa270fa4-f57d-4f6b-9414-f8b62ba20c7c" />



# RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 4: 
To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');


Wc2=Wc(2);

Wc1=Wc(1);



alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) =1-((Wc2-Wc1)/%pi);

else

hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);

end

end

//Hanning Window

for n = 1:M

W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')
[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR BSF using Hanning Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR BSF using Hanning Window');



# OUTPUT: 

<img width="873" height="626" alt="image" src="https://github.com/user-attachments/assets/7e57c49c-f080-41cb-94f0-abce25ec9427" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
