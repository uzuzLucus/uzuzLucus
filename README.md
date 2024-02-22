import pygame
import sys

# Initialiseren van Pygame
pygame.init()

# Scherminstellingen
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Plate Tectonics Adventure")

# Kleuren
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

# Spelvariabelen
plate_x = WIDTH // 2
plate_y = HEIGHT // 2

# Hoofdloop van het spel
def main():
    global plate_x, plate_y

    running = True
    while running:
        screen.fill(WHITE)

        # Verwerken van events
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False

        # Bewegingscontrole van de tektonische plaat
        keys = pygame.key.get_pressed()
        if keys[pygame.K_LEFT]:
            plate_x -= 5
        if keys[pygame.K_RIGHT]:
            plate_x += 5
        if keys[pygame.K_UP]:
            plate_y -= 5
        if keys[pygame.K_DOWN]:
            plate_y += 5

        # Tekenen van tektonische plaat
        pygame.draw.rect(screen, BLACK, (plate_x, plate_y, 50, 50))

        pygame.display.flip()

    pygame.quit()
    sys.exit()

if __name__ == "__main__":
    main()
