- Intergrated Directional Encoding
	- roughness는 spatial MLP의 결과값이다. 
	- roughness를 줄일수록( k값 증가) higher-frequency encoding이 요구된다.  

- Diffuse and Specular Colors
	- ![MLP](./image/MLP.png )
	- 기존의 NeRF와 다르게 Spatial MLP에서는 diffuse, Directional MLP에서는 specular color를 출력한다. specular는 물체의 재질과 반사각을 고려한 color이기 때문에 Reflection과 재질을 고려한 Intergrated Directional Encoding을 통하여 Directional MLP에서 값을 출력한다. 
	- color는 diffuse color와 specular color에 specular tint를 곱한 값의 합으로 구할 수 있다. 

- Accurate Normal Vectors
	- 기존 NeRF에서 normal vector를 구하는 방식은 volume density의 gradient로 구하는 것이다. 
	- 기존 NeRF에서는 물체 내부에 emitter들을 embedding함으로써 fake한 specular highlight를 구현하였다.
	- Ref-NeRF에서는 reflection direction 계산을 위해 predicted normal을 사용한다. 각 ray상의 position에 대해 spatial MLP로 부터 3 vector output을 받아 normalize해 predicted normal을 얻는다. 그 후 기존 NeRF 방식의 normal vector와 묶어 penalty를 준다. MLP를 거치기 때문에 기존 normal vector보다 부드러운 경향을 보인다. 
	- back-facing normal 사용 -> camera 방향과 90도가 넘는 normal에 대해서는 0으로 만든다. 