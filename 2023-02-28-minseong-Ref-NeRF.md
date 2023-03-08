- Intergrated Directional Encoding

![[Pasted image 20230228163156.png]]

기존 NeRF의 positional encoding(sin function 사용)과 다르게 각 direction을 spherical harmonics로 표현한다. 각 component의 encoding은 spherical harmonic function이며 vMF distribution을 사용하였다. 
directional MLP에서 기존 NeRF는 single direction vector를 사용하였는데 Ref-NeRF에서는 reflection vector의 distribution을 사용하였다. 여기서 distribution이 von Mises-Fisher distribution이다. 

- von Mises-Fisher distribution
	- 원 위에서 sampling 되는 data 표현
	- ![[Pasted image 20230228163018.png]]
	-