- 👋 Hi, I’m @dragan77-cmd
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
dragan77-cmd/dragan77-cmd is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---> import pygame
import random

# Koden för Tetris-spelet går här

def main():
    pygame.init()
    fönster = pygame.display.set_mode((FÖNSTER_BREDD, FÖNSTER_HÖJD))
    pygame.display.set_caption("Tetris")

    klocka = pygame.time.Clock()

    rutnät = skapa_rutnät()

    kör = True
    while kör:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                kör = False

        rita_rutnät(fönster, rutnät)
        pygame.display.update()
        klocka.tick(30)

    pygame.quit()


if __name__ == "__main__":
    main()


