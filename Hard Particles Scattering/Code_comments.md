Refer to single_harddisk.pynb

Create a hard disk,

```particle2=sphere(pos=vec(0,0,0), radius=0.1, color=color.black)```

Define the number of scattering particles, arange(start,end,increment),

```range_of_particles = arange(-0.1,0.11,0.01)```

Define the momentum, position, and force on the particles,

```
for i in range_of_particles:
   particle = sphere(color=color.black,radius=0.001)
   attach_trail(particle,radius=0.001,color=color.black)
   particle.F=vec(0,0,0)
   particle.dis=particle.radius+particle2.radius
   particle.mom = vec(15,0,0)
   particle.pos = vec(-2, i, 0)
   yi.append(particle.pos.y)
   particles.append(particle)
```

Create dt that is used for the movement of the particles

```dt=0.00001```
Refer to single_harddisk.pynb
Control when you want the particle to stop,
```
while(t<4):
    rate(1000)
```

Detect collsions between particles and hard disks,
```
    for particle in particles:
        if mag(particle.pos-particle2.pos)<particle.dis:
```
Make the particle bounce off the hard disk,
```
            particle.F=norm(particle.pos-particle2.pos)
            particle.mom = particle.mom+particle.F
        particle.pos = particle.pos + (particle.mom/particle.m)*dt
        t=t+dt
```
 
Creat ang function that defines the scattering angle,
```
def ang(cx,cy):
    #scattering angle
    if((abs(cx)==0) and (cy>0)):
        return (np.pi/2)
    elif((abs(cx)==0) and (cy<0)): 
        return (3*np.pi/2)
    elif((abs(cx)==cx) and (abs(cy)==cy)): #first
        return math.atan2(cy,cx)
    elif((abs(cx)==-cx) and (abs(cy)==cy)): #second
        return math.atan2(cy,cx)
    elif((abs(cx)==-cx) and (abs(cy)==-cy)): #third
        return 2*np.pi+math.atan2(cy,cx)
    elif((abs(cx)==cx) and (abs(cy)==-cy)):  #fourth
        return math.atan2(cy,cx)+2*np.pi
    else:
        return 0
 ```
Add the scattering angle of each particle to the array theta
```
for particle in particles:
    theta.append(ang(particle.pos.x,particle.pos.y))
```


