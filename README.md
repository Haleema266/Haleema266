- 👋 Hi, I’m @Haleema266
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Haleema266/Haleema266 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the display
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption('Player Movement')

# Set up the player
player_size = 50
player_pos = [screen_width // 2, screen_height - player_size]
player_speed = 5

# Game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Get the pressed keys
    keys = pygame.key.get_pressed()

    # Move the player based on the pressed keys
    if keys[pygame.K_UP]:
        player_pos[1] -= player_speed
    if keys[pygame.K_DOWN]:
        player_pos[1] += player_speed
    if keys[pygame.K_LEFT]:
        player_pos[0] -= player_speed
    if keys[pygame.K_RIGHT]:
        player_pos[0] += player_speed

    # Draw the player
    screen.fill((0, 0, 0))  # Clear the screen
    pygame.draw.rect(screen, (255, 255, 255), (*player_pos, player_size, player_size))

    # Update the display
    pygame.display.flip()
