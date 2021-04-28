# pyCO2airseaflux

Python implementation of Wanninkhof (2014) CO2 flux measurement equations.
This software will convert physical ocean observations into air-sea flux (outgassing from the ocean) because an open-source Python version doesn't exist.
This script calculates Schmidt number, CO2 solubility and thus the approximate air-sea CO2 flux. 
Check the papers (bottom) to convert for different gas coefficients.

Example use:
    `from carbon_math import carbon_flux` 
    `print(carbon_flux(33,20,6,425,400))`
where:
    `carbon_flux(salinity,temperature (C),windspeed U,pco2atm,pco2sw,dpco2 (optional))` - Could be updated to take either in a future version, or feel free to fork          it. 


    Parameters
    ----------
    s : Int or Float
        Salinity in PSU (parts per thousand, g/kg).
    t :  Int or Float
        Temperature in Celcius
        (Will conver to kelvin automagically)
    u :  Int or Float
        Windspeed at 10m. (if wsheight!=None, will convert to 10m)
    pco2sw :  Int or Float
        pCO2 in SeaWater (ppm / uatm)
    pco2atm :  Int or Float
        pCO2 in Atmosphere (ppm / uatm)
    dpco2 :  Int or Float, optional
        Delta pCO2 (Difference, atm-sw; ppm/uatm)
        The default is None.
        if Not none, use instead of pco2sw and pco2atm
    wsheight : Int or Float
        Height of windspeed measurement (m)
        The default is None.
        if Not none, convert windspeed to U @ 10m
        using equation 1 in Sutton et al., (2017)
        
        
Sources:
Sutton, A. J., Wanninkhof, R., Sabine, C. L., Feely, R. A., Cronin, M. F., & Weller, R. A. (2017). Variability and trends in surface seawater p CO 2 and CO 2 flux in the Pacific Ocean: Pacific Ocean CO 2 Flux Trends. Geophysical Research Letters, 44(11), 5627–5636. https://doi.org/10.1002/2017GL073814
Wanninkhof, R. (2014). Relationship between wind speed and gas exchange over the ocean revisited. Limnology and Oceanography: Methods, 12(6), 351–362. https://doi.org/10.4319/lom.2014.12.351
Weiss, R. F. (1974). Carbon dioxide in water and seawater: The solubility of a non-ideal gas. Marine Chemistry, 2(3), 203–215. https://doi.org/10.1016/0304-4203(74)90015-2
