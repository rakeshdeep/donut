# Donut - ASCII Donut Renderer


This project demonstrates a fascinating and compact way to render a 3D rotating torus (donut) in ASCII characters using C. The program implements 3D projection mathematics, leveraging framebuffer and z-buffering to create a mesmerizing effect in the terminal.


**Donut:**

```
                           i,j,k,x,y,o,N;
                      main(){float z[1760],a
                    #define R(t,x,y) f=x;x-=t*y\
                 ;y+=t*f;f=(3-x*x-y*y)/2;x*=f;y*=f;
                 =0,e=1,c=1,d=0,f,g,h,G,H,A,t,D;char
               b[1760];for(;;){memset(b,32,1760);g=0,
              h=1;memset(z,0,7040);for(j=0;j<90;j++){
              G=0,H=1;for(i=0;i<314;i++){A=h+2,D=1/(G*
              A*a+g*e+5);t=G*A        *e-g*a;x=40+30*D
              *(H*A*d-t*c);y=          12+15*D*(H*A*c+
              t*d);o=x+80*y;N          =8*((g*a-G*h*e)
              *d-G*h*a-g*e-H*h        *c);if(22>y&&y>
               0&&x>0&&80>x&&D>z[o]){z[o]=D;b[o]=(N>0
                ?N:0)[".,-~:;=!*#$@"];}R(.02,H,G);}R(
                .07,h,g);}for(k=0;1761>k;k++)putchar
                 (k%80?b[k]:10);R(.04,e,a);R(.02,d,
                   c);usleep(15000);printf('\n'+(
                     " donut.c! \x1b[23A"));}}
                        /*no math lib needed
                          .@rakeshdeep 2025.*/
```

## How It Works

At its core, the program:
1. **Renders 3D Objects in ASCII**: The donut surface is mapped onto a 2D ASCII plane.
2. **Mathematics of 3D Projection**: Uses trigonometric functions to calculate the donut's perspective and rotation.
3. **Illumination**: Simulates lighting effects with ASCII characters of varying intensity (`.,-~:;=!*#$@`).
4. **Optimization**: Efficiently handles calculations with integer arithmetic and bit-shifting for speed.

## Code Breakdown

- **Buffers**: 
  - A framebuffer (`b`) to store ASCII characters.
  - A z-buffer (`z`) to manage depth and ensure the correct rendering of overlapping areas.
  
- **Rotation Functions**: 
  - Macro `R` rotates coordinates around an axis using trigonometry.

- **Main Logic**:
  - Iterates over angles `i` and `j` for the torus's 3D surface.
  - Calculates 2D screen coordinates for each point on the surface.
  - Updates the framebuffer and z-buffer for proper rendering.

- **Output**:
  - Continuously outputs the updated ASCII donut to the terminal, simulating rotation.

## Running the Program

### Prerequisites
- A C compiler (e.g., `gcc`).
- A terminal supporting ANSI escape codes.

### Compile and Run
1. Compile the code:
   ```bash
   gcc -o donut main.c
