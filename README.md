# Weekly-Reports


## Week 1:
* Git basics
* Installed PLUTO on rc1
* Installed VisIt on rc1
* Tested PLUTO functionality 
* Imported test data into VisIt, made visualizations of Orszag-Tang test

## Week 2:
*This week's report includes numerous animations in the form of .gif files. Many of these animations can be found in respective test folders under the 'Magnetar-PLUTO-files' repository*. 

* Creation of init.c file for disk of uniform density
* Creation of 'Magnetar-PLUTO-files' repository
* Switch to polar coordinates
* Inclusion of N = 1 polytropic density, pressure, and gravitational potential
* Issues with r = 0 region causing unwanted velocity perturbations  
* Inclusion of "Non-dimensional units"
* Development of negative densities resulting in code failure
* Possible issues with potential across r = R = 1 boundary

## Week 3:
* Work in spherical coordinates
* Unit bases defined in *definitions.h*
* Normalization procedure in *init.c*
* Fix normalization procedure
* Specify abiabtic index (gamma = 2)
* Internal boundary condition near r = 0

## Week 4:
* SSH into "research-computer-1", ran longer term simulation through t = 5 s 
* Instability occuring around t = 0.9 s
* Defined unit normalization for gauss in cgs bases
* Read through Haskell et al. 
* Reparameterized Haskell B-field equations for normalized radius

## Week 5:
* Transition to MHD module in PLUTO after having used the HD module 
* Negative density errors develop rapidly, shows that model is still unstable
* Unusual disjunction found near r = 1.0 in pressure profile
* Boundary condition set for outermost region of computational domain
* Change to "hllc" numerical solver which has greater accuracy than prior methods
* Implement pressure floor for forcing non-negative pressure/density terms from dropping below zero. 
* Find stability with MHD module after implementing pressure floor. 

## Week 6:
* Tested "roe" solver, compared results with "hllc" numerical method. 
* Coded poloidal and toroidal components into *init.c*
* Including B-field equations in simulation quickly leads to errors in simulation. 
* NVidia drivers updated for "research-computer-1"

## Week 7-8 (Fall Break):
* Problem conditioning with Haskell b-field equations
* Computes relative condition numbers for b-field equations to determine the behavior of the equations
* Verifies that equations are generally well behaved over our computational domain
* *Condition_Grid_Analysis.py* analyzes radial grid points to determine if the b-field equations are well behaved at the specified points. If not, poorly behaved locales are printed to the console. 
* *Grav_Pot.py* graphs the gravitational potential by porting the equations from *init.c*
* Require piecewise continuity, however, we see that for 0<r<1 the potential is lower in magnitude than it should be. 
* Issue was that stellar mass was improperly defined in the region. Value was updated and potential was verified smooth after corrections were made. 
* Allows removing some internal boundary conditions. 
* Introduce non-uniform grid spacing within the star, cleans up results well. 

## Week 9:
* I was having plenty of setbacks with the magnetic field as I attempted to simulate both stable stellar structure along with a b-field. As a result, this is a week that I did not have meaningful results to report. 

## Week 10:
* Create spreadsheet of boundary conditions for the b-field, organizes what value the field takes in different regions. 
* Create user-defined boundary conditions in *init.c* for the b-field
* Achieve successful simulation of b-fields, testing excessively powerful field of magnitude 10^17 gauss
* *B_field_analysis.py* plots b-field components as my coded equations specify, called to mind useful addition of further necessary boundary conditions
* Corrected b-field normalization
* Simulation of corrected results
* Comparing b-field with Kuhn's work

## Week 11:
* Simulated results with B-field magnitude set to zero. Verify that we see results similar to prior HD simulations.
* Slight correction to B-field normalization, include (4pi)^-1/2 term, magnitude of b-field agrees much more closely with Kuhn results. 
* Convert simulation back into cgs, requires edits in *pluto.ini* for converting density, pressure
* Convert user-defined variables for b-field components nback to cgs
* Disable "Automatic Suspend" for "research-computer-1". This allows continous and unimpeded operation for simulations. 
* Match b-field boundary conditions at r = 1 
* Set internal boundary condition that toroidal component is stricly zero outside the star

## Week 12:
* Compared effect of resolution on simulations
* Ran 57 hour simulation for high-res data, determined that there is no considerable difference between results with high/low res results. 
* Allows us to use lower-res simulations for relatively quick computation.

## Week 13:
* For personal reasons, this week was particularly challenging, and as such, I did not have the occasion to work on research during this time. 

## Week 14:
* Vector field correction: verified that VisIt assumes a cartesian coordinate system, conflicts with how b-field and v-field components are defined using spherical coordinates in *init.c* 
* Require transformation expressions, see *VisIt_Spherical_to_Cartesian.txt"*
* Verify transformations are justified and that expressions for r, theta, and phi correspond to proper respective regions.
* Graph corrected results. 
* Notice interesting results with velocity perturbations on the surface of the star
* Figured out how to create streamline graphics for the b-field to assist in showing field structure. 

## Research Seminar Presentation (11-29-18)
* Present research and findings that I have been working on this semester with other departmental honors thesis candidates.  


