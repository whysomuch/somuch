# somuch
a repository
import pygame
import sys
from pygame.locals import *
pygame.init()
screem=pygame.display.set_mode((720,760))
pygame.display.set_caption('my first work')
speed=[0,5]
color=(0,0,0)
city=pygame.image.load(r"C:\city1.png")
cityrect=city.get_rect()

fps=60
fclock=pygame.time.Clock()
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()
    cityrect=cityrect.move(speed)
    if cityrect.bottom>760 :
        speed=[0,-5]
    elif cityrect.top<0:
        speed=[0,0]

    screem.fill(color)
    screem.blit(city,cityrect)
    pygame.display.flip()
    pygame.display.update()
    fclock.tick(fps)
pygame.quit()
