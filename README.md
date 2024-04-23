# rconst_cp2k
A homebrew version based on CP2K v8.2 which with rotational/roto-translational constraint method implemented

## Usage
The constraint method can be used as other official constraint methods in CP2K, here is a little example
```
...
&COORD !Cartesian coordinates of system
	N  -0.00000000    0.00000000   -0.09999998  M1
	H   0.00000000    0.95223715    0.23666663  M1
	H   0.82466156   -0.47611858    0.23666663  M1
	H  -0.82466156   -0.47611858    0.23666663  M1
	N   1.61846237    3.12648673    1.12207349  M2
	H   1.61846237    4.07872389    1.45874010  M2
	H   2.44312393    2.65036816    1.45874010  M2
	H   0.79380080    2.65036816    1.45874010  M2
	N  -0.94386640   -1.51381415    2.30701324  M3
	H  -0.94386640   -0.56157700    2.64367985  M3
	H  -0.11920484   -1.98993273    2.64367985  M3
	H  -1.76852797   -1.98993273    2.64367985  M3
&END
...	
&CONSTRAINT !Constraint settings
	CONSTRAINT_INIT T
	&ROTC !Rotational/roto-translational constraint settings
		MOLNAME M1
		ATOMS 1 2 3 4
		POSITIONS0  [ANGSTROM] -0.00000000    0.00000000   -0.09999998  0.00000000    0.95223715    0.23666663  0.82466156   -0.47611858    0.23666663  -0.82466156   -0.47611858    0.23666663
	&END ROTC
&END CONSTRAINT
```

## Installation
We put the roto-translational constraint version in `src_rt` and the rotational constraint version in `src_roto`. Users can replace the source code in the official version CP2K with the code and then install it as a normal version.
