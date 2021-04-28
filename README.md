# pyCO2airseaflux
Convert ocean physical observations into an airsea flux (Python version)

This small package allows the user to calculate air-sea CO2 flux from observations. The main function is `carbon_flux`. You should call it like `from carbon_math import carbon_flux


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
