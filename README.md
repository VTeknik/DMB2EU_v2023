# DMB2EU_v2023
%==========================================================================
% This Matlab code is devoloped estimation of Depth to Magnetic Basement(DMB), 
% using Radially Avaraged Power Spectrum(RAPS)method magnetic data.
% ========================Functins========================================
%  list of the functions:
%   ==>[x,y,mag,long,lat] = ldata  : Loads magnetic data 
%   ==>[win_l,overlap,beta,cs,dcs,per] = getpar  : Gets input parameters

%   ==>[point_xy] = pointxy(x,y,win_l,overlap) : defines window centers within the whole
%   data. 
%   ==>[np, halfy,topout] = par(point_xy,cs) : Define some paremeters
%   ==>[Index_win,n_win_p] = windata(point_xy,nn,win_l,halfy,x,y,cs,per)
% widowing data
%   ==>   MAG_W = nanremove(MAG_W) : remove nan value of grid and replace with
%   mean value.
%   ==>[X,Y,MAG] = griding(x,y,mag,cs) : grid magnetic data with xyz format data
%   ==>winfunc = winfun(nx,ny) :creat window function for correctting Gibbs
%   phenomena
%   ==>[kx,ky] = wavenumber(nx,ny,cs); % defines wavenumber
%   ==>[k_r,log_k_r,RAPS,LOG_RAPS] = rapspec(mag_fft,k); %calculate Radial Average Power Spectrum
%   ==> phi_fun : basic function furmulla
%   ==> phi_k1=theory(beta,zt,dz,c1,k_r); % RAPS graph based on formula 
%==========================================================================
