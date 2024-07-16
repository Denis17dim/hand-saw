# hand-saw
import pygame
import sys

# Инициализация Pygame
pygame.init()

# Настройка дисплея
width, height = 800, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Простая ручная пила")

# Определение цветов
grey = (169, 169, 169)
dark_grey = (105, 105, 105)
brown = (139, 69, 19)

# Функция для рисования ручной пилы
def draw_saw():
    # Лезвие пилы
    pygame.draw.polygon(screen, grey, [(200, 300), (600, 300), (580, 320), (220, 320)])
    for i in range(20):
        pygame.draw.polygon(screen, dark_grey, [(200 + i*20, 320), (210 + i*20, 340), (220 + i*20, 320)])
    # Рукоятка пилы
    pygame.draw.rect(screen, brown, (150, 250, 100, 50))
    pygame.draw.circle(screen, brown, (150, 275), 25)
    pygame.draw.circle(screen, brown, (250, 275), 25)

# Основной цикл
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    screen.fill((255, 255, 255))  # Заполнение фона белым цветом
    draw_saw()  # Рисование пилы
    pygame.display.flip()  # Обновление дисплея

pygame.quit()
sys.exit()
