-------------------------------------------------------------------------------------------------------
How to create a new user-defined test-case:

1. duplicate the directory test1 and rename it (e.g. "user_test")
2. copy the user's files "stl1.stl", "stl2.stl",  etc inside "user_test"
3. customize the simulation data between %% BEGIN USER SETTINGS and %% END USER SETTINGS
    Description/Example:
    %% BEGIN USER SETTINGS
    paraview_export_flag = 1; % if 1 export paraview files in "res_para" directory
    x_ray_flag = 1;           % if 1 make x_ray plot
    model_name='mytest';         % name of the model
    %
    stl_files(1).name = 'test.stl'; % name of the first stl file to load
    stl_files(1).tag = 'cond';          % tag for the material (write 'cond' for condutive media)
    stl_files(1).rho=1/57e6;            % conductivity of the medium
    % Box 
    % number of voxels in the x y z directions
    Nx=100; number of voxels in the x direction
    Ny=100; number of voxels in the y direction
    Nz=8;   number of voxels in the z direction
    % corners
    flag_auto=1; % if 1, user_data below are ignored and the box is created automatically (suggested)
    % user_data   corners of the Box
    meshXmin = -6e-3;      % (m)        
    meshXmax = 4.5e-3;     % (m)
    meshYmin = -4e-3;      % (m)
    meshYmax = 3.5e-3;     % (m)
    meshZmin = 0;          % (m)
    meshZmax = 0.4e-3;     % (m)
    %% END USER SETTINGS
3. run "mainVOXELISE.m"

File "data.mat" is now created and you can select "user_dir" in "FFT_VI.m" 
to select the user test case
-------------------------------------------------------------------------------------------------------
