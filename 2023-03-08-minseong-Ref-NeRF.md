- Experiment
	- 기존 NeRF와 Ref-NeRF를 비교하기 위해 같은 dataset으로 train을 진행한 후 특정 camera 시점에서 view synthesis를 진행해 보았다. 
	- ![[Pasted image 20230308113941.png|200]]  ![[Pasted image 20230308114111.png|200]]  ![[Pasted image 20230308114200.png|200]]
	- 가장 왼쪽 사진은 testset의 ground truth이며 다음 rendering된 사진들이 각각 NeRF와 Ref-NeRF이다. 
	- NeRF rendering 결과는 psnr값이 28.31로 Ref-NeRF의 37.81보다 낮았다. NeRF의 경우 대부분의 자동차의 결과가 잘 나왔지만 specular surface의 rendering이 부분적으로 실패하였다. 

- Code Review
	- 