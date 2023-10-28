[back to index](Index.md)

# SciPy Constants

Using those Constants needs to import the *constants* module.
```
from scipy import constants

print(constants.liter)
```

The full list is here: [constants.html](https://docs.scipy.org/doc/scipy/reference/constants.html)  
Some examples:

## Mathematical constants

| name | Comment |
| --- | --- |
| *pi* | Pi |

## Physical constants
| name | Comment |
| --- | --- |
| *c* **or** *speed_of_light* | speed of light in vacuum |
| *mu_0* | magnetic permeability µ0 |
| *epsilon_0* | vacuum permittivity ε0 |
| *h* **or** *Planck* | the Planck constant |
| *G* **or** *gravitational_constant* | Newtonian constant of gravitation |
| *g* | *standard acceleration of gravity* |
| *e* **or** *elementary_charge* | elementary charge |
| *k* **or** *Boltzmann* | Boltzmann constant |
| *m_e* **or** *electron_mass* | electron mass |

## Constants database

**scipy.constants.physical_constants** is a Dictionary of physical constants, of the format  
*physical_constants[name] = (value, unit, uncertainty)*.

Example:
```
print(constants.physical_constants["Boltzmann constant"])
# (1.380649e-23, 'J K^-1', 0.0)
```

| name | value and unit |
| --- | --- |
| *atomic mass constant* | 1.6605390666e-27 kg |
| *atomic unit of charge* | 1.602176634e-19 C |
| *Boltzmann constant* | 1.380649e-23 J K^-1 |
| *Boltzmann constant in eV/K* | 8.617333262e-05 eV K^-1 |
| *characteristic impedance of vacuum* | 376.730313668 ohm |
| *Compton wavelength* | 2.42631023867e-12 m |
| *electron mass* | 9.1093837015e-31 kg |
| *electron mass energy equivalent in MeV* | 0.51099895 MeV |
| *electron volt* | 1.602176634e-19 J |
| *Elementary charge* | 1.602176634e-19 C |
| *joule-electron volt relationship* | 6.241509074e+18 eV |
| *kelvin-electron volt relationship* | 8.617333262e-05 eV |
| *molar gas constant* | 8.314462618 J mol^-1 K^-1 |
| *molar mass constant* | 0.00099999999965 kg mol^-1 |
| *Planck constant* | 6.62607015e-34 J Hz^-1 |
| *Planck constant in eV/Hz* | 4.135667696e-15 eV Hz^-1 |
| *Planck length* | 1.616255e-35 m |
| *Planck mass* | 2.176434e-08 kg |
| *Planck time* | 5.391247e-44 s |
| *speed of light in vacuum* | 299792458.0 m s^-1 |
| *standard acceleration of gravity* | 9.80665 m s^-2 |
| *standard atmosphere* | 101325.0 Pa |
| *Stefan-Boltzmann constant* | 5.670374419e-08 W m^-2 K^-4 |
| *vacuum electric permittivity* | 8.8541878128e-12 F m^-1 |
| *vacuum mag. permeability* | 1.25663706212e-06 N A^-2 |

## SI prefixes
All standard SI prefixes are available as lowercase: giga, tera, micro, ...
## SI prefixes
All standard binary prefixes are available as lowercase: kibi, mebi, gibi, tebi, ...

## useful mass units in kg
* gram 10^-3
* metric_ton 10^3
* lb - one pound
* oz - one ounce

## useful angle units in radians
* degree

## useful time units in seconds
* minute, hour, day, week, year
* Julian_year - 365.25 days

## useful length units in meters
* inch, foot, yard, mile, mil, micron
* light_year, parsec, astronomical_unit

## useful pressure units in pascals
* bar, torr, psi

## useful pressure units in cubic meters
* liter
* gallon (US), gallon_imp (UK)

## useful speed units in meters per second
* kmh
* mph
* mach
* speed_of_sound
* knot

## useful temperature units in Kelvin
* zero_Celsius

## useful energy units in Joule
* eV
* calorie

## usefule power units in watts
* hp (horse_power)

## usefule force units in newtons
* kgf (one kilogram force in newtons)

[back to index](Index.md)
