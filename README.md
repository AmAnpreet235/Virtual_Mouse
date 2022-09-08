# Virtual_Mouse
Motivation
 motivation behind doing this project 
or situation where we can apply this project 

As we alll known in this ongoing pandemic alll of us avoid to touch public place 
because we all know if we touch any sensitive place or infected place it may  infect us ...

so for the places where we cant avoid touch them and use sanitizer on it like atm of banks , online automating ticket booking of metro where we all have to touch the screen as of our requirement 

so if we can have a software where we can perform this operation without touching it ... 
by use of virtual mouse so its gr8 help .This project  proposes a way to control the position of the cursor with the bare hands without using 
any electronic device. While the operations like clicking objects will be performed with different 
hand gestures. The proposed system will only require a webcam as an input device.

challenges ==
As I started working on this project 
in the first step i faced a big challenge like" how to detect hand of the user"???

to solve this probelm i search on the internet and found so many solution but i found two of them is more suitable
one is to use create dataset and storeed all the images of hand like if user can show there hand in x way, y way ,z way 
but if i have to go with this solution i have to spend so much of time on internet to search image of hand in every possible way so i drop this idea 

and i choose second idea like if i am deviding my palm of hand in some points and for performing any operation calculate the differnce between this points it will be really easy to solve 

so i consider there are 21 points in user palm like in every finger from the tip it starts and till the joining each finger to the plam each one have 4 so 4*5 =20 
and one is middle of palm ..


The first step is to activate the camera so that the input can be 
provided to the system for this to happen we need to assign the 
resources of the camera to a variable the command that will be 
used for this purpose is cam=cv2. Video Capture(0) this 
command will activate the camera that is connected to the 
system and will be able to take the input from the camera as 

so now i am deviding this project in two module 
1.hand detection 
2.perform operation on this points
 So now i am in hand detection module 
 so for detect points on user hand we required image of user hand 
 so we open the camera with the help of opencv library present in python 
 **open cv 
 OpenCV is a huge open-source library for computer vision, machine learning,and image processing. OpenCV supports a wide variety of programming languages like Python, C++, Java, etc. It can process images and videos to identify objects, faces, or even the handwriting of a human. When it is
 integrated with various libraries, such as Numpy which is a highly optimized library for numerical operations, then the number of weapons increases in your Arsenal i.e whatever operations one can do in Numpy can be combined with OpenCV.

 So here i am creating one list for stroign all this points after succesfully detection with the help of numpy library 

 **NumPy is a Python library used for working with arrays.It also has functions for
working in domain of linear algebra, fourier transform, and matrices
In Python we have lists that serve the purpose of arrays, but they are slow to
process.NumPy aims to provide an array object that is up to 50x faster than
traditional Python lists.

so our biggest challenge is solve so far 

**new challenge comes like i have to select one finger for moving curson and one gesture for clicking on object 

so for moving cursor i select index finger beacuase almost all of us performing click opertion on mouse with index finger only 

so for moving cursor ->
	now if user want to move cursor and if the index finger of user is up or if we have dimension of tip od index finger is above our theshold we say user want to perform moving operation ....
	so we stored this points dimension in some varible liek prevLocX,prevLocY 
	and till user not stopped mvoing its hand . after user stoped its moving hand we stroed this dimension in some varivle like curLocX,curlocY 
	and we perform moving the cusor to this distanceby calculating distnace between this 2-d points 
	and every time we are updating this points also like curr become previn this way 

	as this points are not freezable for evry pc because every pc have some differnt configuration so we smooth this value according to our configuration  like 360/480 480/640 720/1080

	so after having smmothing coordinates and distanve to move
	we can simple calll move function of autopy library with the folowing paramete 
	(starting cordinates ,distance,ending cordinates )


	**now for clicking operation ->
	we check if coordinate of tip of index finger and middle finger and distnce between this points is less than our thershold we perform click opertion ...

	So in this way we can perfom al the operation of mouse without touching mouse..
	thats alll about my project
