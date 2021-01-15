# CudaPathTracer
A simple GPU accelerated ray tracer built using CUDA C++, OpenGL, and C++

The window is built using GLFW library, and a Pixel Buffer Object (PBO) is built to allow CUDA to communicate with OpenGL. The path tracing calculations are done using a CUDA kernel, which then write data into a CUDA buffer. A second kernel sends data from the buffer into the PBO, which is then rendered onto the window.

So far, the path tracer can show Global Illumination of three different types of materials: diffuse, specular, and refracting (dielectric). These are calculated using, respectively, ideal Lambertian BRDF, law of reflection, and smooth dielectric BSDF.

On my gtx 1070ti, the pathtracer is able to get 60fps with about 1 sample per pixel with 10 bounces. Increasing the number of bounces to beyond 50 drops speed to about 30fps.


Example Images

![Refraction, Diffuse, and Specular](https://github.com/EsteBran/CudaPathTracer/blob/main/example%20refract%20kind%20of%20working.JPG)
![Specular and Diffuse](https://github.com/EsteBran/CudaPathTracer/blob/main/example%20spheres.JPG)
