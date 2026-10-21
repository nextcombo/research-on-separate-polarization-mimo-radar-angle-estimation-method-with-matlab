# Research on Separate Polarization MIMO Radar Angle Estimation Method [with MATLAB Code]

Signal model
Figure 1: A schematic diagram of a single isolated crossed dipole
In the OT direction, the array elements of classical co-pointed crossed dipoles have responses [6]:
The spatial orientation vectors of the two dipole components are equal to:
Now consider a single-baseline polarization MIMO radar system, where the transmit array consists of M single-polarization elements arranged horizontally along the x-axis to form an uniform linear array with a spacing of td. The receive array is an uniform linear array composed of cross-coupled dipoles as shown in Figure 1, with N elements. The radar system structure is depicted in Figure 2. Here, the transmit array elements are formed by the x components of the receive array elements, meaning that both transmission and reception are co-located.
Figure 2: Diagram of a Separate-Dipole MIMO Radar with Polarization
After receiving the signal and matching filtering, the signal model of the polarized MIMO array radar can be represented as [6].
According to array signal processing theory, the transmitting array spatial steering vector and receiving array spatial steering vector of the kth target are respectively equal to:
Based on the BOMP perspective and polarization joint estimation, according to the analysis in the previous section, by processing the signal after matched filtering of a single-baseline polarization MIMO radar system, it is possible to achieve joint estimation of target angle and polarization parameters. The following discusses a method for joint angle and polarization parameter estimation through fast sparse optimization using BOMP, which only requires constructing a sparse dictionary in the angle dimension.
MATLAB simulation
Figure 3 presents the estimated positions and their amplitudes of support points calculated by this section's algorithm. For convenience, here we set the interval of the dictionary to 1° and the range of angles to [0°, 180°]. Theoretically, the first point of the actual support position should be 41 and 121, respectively. Here, the signal-to-noise ratio (SNR) is 20dB and the number of frames is 1000. From the figure, it can be seen that through simulation calculations, the first point of the estimated support position in this section's algorithm is X=41 and 121, which are consistent with the theoretical values. Therefore, it can be concluded that using this section's algorithm, the target's support position can be accurately restored.
MATLAB code demonstration
%%%Separated polarization MIMO radar angle and polarization joint estimation clc; clear; close all; j=sqrt(-1); M=4; % Number of transmitting antennas N=4; % Number of receiving antennas snap=100; % Quick shot count = 1; %Monte Carlo experiment count a=[0:M-1]'; % Launch array vector b = [0:N-1]' % Receive array vector c = 3e8; f=300e6; lamda=c/f; % Wavelength lambda = lamda;% The received element spacing dt = lambda; % The spacing between the emitted elements d1=lambda/2; %Separation of cross-dipoles in space P=2; % Number of signal sources: sita = [10, 30]*pi/180; gamma=[45 45]*pi/180; yita=[-90 90]*pi/180; % Target parameter a_t = exp(-j*2*pi/lambda*dt*a*sin(sita)); % Launching the steering vector a_r = exp(-j*2*pi/lambda*dr*b*sin(sita));% Received steering vector a_s = exp(-j*2*pi/lambda*d1*sin(sita)); %% Spatial phase shift factor v = [-cos(gamma); a_s.*sin(gamma).*cos(sita).*exp(j*yita)]; % Polarization-oriented Vector A_mimo = [kron(a_r(:, 1), a_t(:, 1)) kron(a_r(:, 2), a_t(:, 2)) ]; %MIMO radar's steering vector A=[kron(A_mimo(:, 1), v(:, 1)) kron(A_mimo(:, 2), v(:, 2)) ];% Polarized MIMO radar's steering vector s = exp(j*rand(P, snap)*2*pi); % Receive signal tic%% Construct dictionary matrix grid_angle=1; %% Search angle interval. Unit is degree%angle_grid=[(min(sita)*180/pi-5):grid_angle:(max(sita)*180/pi+5)]/180*pi; %% Angle grid for pitch and yaw sparse angles%% Angle grid length for pitch-yaw sparse angles:
theta_len = length(angle_grid); % Length of angle grid for angle parameters search

Note: The above code is in Chinese and does not provide a translation.
End

## Images

![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](01.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](02.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](03.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](04.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](05.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](06.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](07.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](08.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](09.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](10.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](11.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](12.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](13.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](14.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](15.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](16.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](17.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](18.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](19.jpg)
![(DOA Estimation)Research on Separate Polarization MIMO Radar Angle Estimation Method [Attached MATLAB Code]](20.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
