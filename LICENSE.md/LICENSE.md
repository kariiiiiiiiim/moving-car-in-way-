from OpenGL.GLU import *
from OpenGL.GLUT import *
import numpy as np
from OpenGL.GL import *
from math import *

x=0
f=True
z=0
def myinit():
    glMatrixMode(GL_PROJECTION)
    glClearColor(1,1,1,1)
    glClear(GL_COLOR_BUFFER_BIT)
    gluPerspective(50,1,.1,50)
    gluLookAt(14,10,8,0,0,0,0,1,0)

def draw():
    glClear(GL_COLOR_BUFFER_BIT)
    global x
    global f
    global z
    glMatrixMode(GL_MODELVIEW)
    # way
    glLoadIdentity()
    glColor3f(.192, .192, .192)
    glTranslate(0, -1.80, 0)
    glScale(50, .5, 10)
    glutSolidCube(1)
    #tree
    glLoadIdentity()
    glColor3f(.153,0,0)
    glTranslate(5,-1.5,-5)
    glRotate(90,1,0,0)
    glScale(1,1,-5)
    glutSolidCylinder(1,2,10,10)
    glColor3f(0,1,0)
    glRotate(90, 1, 0, 0)
    glTranslate(0,2,0)
    glScale(7,10,5)
    glutSolidSphere(1,2,20)




    #kber
    glLoadIdentity()
    glColor3f(0,0,0)
    glTranslate(x,0,0)
    glScale(1,.25,.5)
    glutWireCube(5)
#so8ayr
    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(0,1.25,0)
    glScale(.5,.25,.5)
    glutWireCube(5)

    glColor(1,0,1)
    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(2,-.5,1.25)
    glRotate(-z,0,0,1)
    glutWireTorus(.125,.5,12,8)

    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(-2,-.5,-1.25)
    glRotate(-z,0,0,1)
    glutWireTorus(.125,.5,12,8)

    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(2,-.5,-1.25)
    glRotate(-z,0,0,1)
    glutWireTorus(.125,.5,12,8)

    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(-2,-.5,1.25)
    glRotate(-z,0,0,1)
    glutWireTorus(.125,.5,12,8)


    glColor(1,1,0)
    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(2,-.3,.4)
    glutSolidSphere(.3,20,20)

    glLoadIdentity()
    glTranslate(x,0,0)
    glTranslate(2,-.3,-.4)
    glutSolidSphere(.3,20,20)

    # 3wamed in the way
    glLoadIdentity()
    glColor3f(.165, .42, .42)
    glScale(1, 25, 1)
    glTranslate(0, .1, 4.2)
    glutSolidCube(.3)
    glColor3f(1,0,0)
    glScale(1,.05,1)
    glTranslate(0, 2.3, 0)
    glutSolidSphere(1,20,2)
    #tany
    glLoadIdentity()
    glColor3f(.165, .42, .42)
    glScale(1, 25, 1)
    glTranslate(-8, .1, 4.2)
    glutSolidCube(.3)
    glScale(1, .05, 1)
    glTranslate(0, 2, -.1)
    glRotate(-45,1,0,1)
    glutSolidCylinder(1,2,15,10)
    glColor3f(1,1,0)
    glutSolidCone(1,1,10,4)





    if x > 7:
      f = False

    if x < -14:
        f = True

    if f:
        x+=.001
        z-=1
    else:
        x-=.001
        z+=1
    glFlush()

glutInit()
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutInitWindowSize(600,600)
glutCreateWindow(b"looool")
myinit()
glutDisplayFunc(draw)
glutIdleFunc(draw)
glutMainLoop()

