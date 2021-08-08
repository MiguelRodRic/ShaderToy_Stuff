# ShaderToy_Stuff
Summary of the small prototypes I implement in ShaderToy.



## Soft Shadows 
Implemented 2 versions of a simple soft shadow technique. Both of them use basic cone tracing to sample shadow rays to the light source by just displacing horizontally the light source each different ray. 
The first version uses a brute force approach with a very high number of shadow rays traced per pixel (16 * 16) to get very nice visual results at the expense of quite bad performance.
The second version reduces the shadow ray amount by 1/4 of the original for much better performance but worse visual results, there is some noticeable color banding in the penumbra area. I used a blue noise texture in the penumbra area to mitigate a bit the banding artifacts.

Brute force approach:
https://www.shadertoy.com/view/stjSzV
![Shadow_BruteForce](https://user-images.githubusercontent.com/17479836/128628616-77be88ce-3fa9-4138-bcc1-a679cd4a6822.PNG)

Cheap approach with blue noise:
https://www.shadertoy.com/view/ftBSR3
![Shadow_BlueNoise](https://user-images.githubusercontent.com/17479836/128628648-fb661c3d-86bf-478a-96a8-292688b0eb75.PNG)
