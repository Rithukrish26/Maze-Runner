import pygame
import sys
pygame.init()
screen_width = 1290
screen_height = 737
running=True

screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Pygame Basics")
background_color = ('black')
play_button=pygame.Rect(575,268.5,200,50)
exit_button=pygame.Rect(575,268.5+80,200,50)

def maze():
    background_color = 'dark grey'
    score = 0

    maze = [
        [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 ,1 ,1 ,1 ,1 ,1 ],
        [1, 0, 0, 0, 0, 0, 0, 0, 10, 1, 1, 1, 1, 1, 0, 0, 0, 1, 50, 1 ,1 ,1 ,1 ,1 ,1 ],
        [1, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 1, 1, 0, 1, 0, 0, 0, 1 ,50 ,0 ,1 ,1 ,1 ],
        [1, 0, 1, 1, 1, 1, 1, 1, 0, 1, 0, 1, 1, 0, 0, 1, 1, 0, 0, 1 ,1 ,0 ,1 ,1 ,1 ],
        [1, 0, 0, 0, 0, 0, 1, 1, 0, 1, 0, 0, 0, 0, 1, 1, 1, 1, 50, 0 , 1 , 0, 1 , 1 ,1 ],
        [1, 1, 1, 1, 1, 50, 40, 0, 0, 0, 30, 40, 1, 1, 1, 0, 1, 1, 0, 1 ,1 ,0 ,1 ,1 ,1 ],
        [1, 0, 1, 1, 1, 0, 0, 0, 1, 1, 0, 1, 1, 0, 0, 0, 1, 0, 0, 0 ,0 ,0 ,1 ,1 ,1 ],
        [1, 0, 0, 0, 0, 0, 1, 50, 1, 0, 0, 1, 1, 0, 1, 0, 1, 0, 1, 0 ,1 ,0 ,1 ,1 ,1 ],
        [1, 30, 40, 1, 1, 1, 1, 0, 0, 1, 0, 0, 0, 0, 1, 1, 1, 0, 1, 1 ,0 ,30 ,40 ,1 ,1 ],
        [1, 30, 40, 1, 30, 1, 30, 0, 0, 1, 1, 0, 1, 1, 1, 0, 0, 0, 0, 1 ,1 ,0 , 0, 1 ,1 ],
        [1, 30, 40, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 0, 1, 1, 1, 0, 50, 40 ,1 ,0 ,1 ,0 ,1 ],
        [1, 0, 0, 0, 1, 0, 0, 1, 0, 1, 1, 0, 1, 0, 0, 0, 30, 40, 0, 40 ,0 ,30 ,40 ,1 ,1],
        [1, 1, 1, 0, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 1, 0, 1, 1, 20, 1 ,1 ,1 ,1 ,1 ,1 ],
        [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 ,1 ,1 ,1 ,1 ,1 ],
    ]

    black = pygame.Color('black')
    white = pygame.Color('white')

    tile_size = 55

    player_row, player_column = 1, 8

    running = True
    background_tile=pygame.image.load('bg.jpg')
    background_tile=pygame.transform.scale(background_tile,(tile_size,tile_size))

    path_tile = pygame.image.load('26667.jpg')
    path_tile = pygame.transform.scale(path_tile, (tile_size, tile_size))

    char=pygame.image.load('character_-removebg-preview.png')
    char=pygame.transform.scale(char,(tile_size-5,tile_size-5))

    cash = pygame.image.load('OIP.jpeg')
    cash = pygame.transform.scale(cash, (tile_size - 5, tile_size - 5))

    spike = pygame.image.load('Spikeyyyy.png')
    spike = pygame.transform.scale(spike, (tile_size - 5, tile_size - 5))

    hole = pygame.image.load('hole.jpg')
    hole = pygame.transform.scale(hole, (tile_size - 5, tile_size - 5))

    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False

        keys = pygame.key.get_pressed()
        new_row, new_column = player_row, player_column

        if keys[pygame.K_UP]:
            new_row -= 1
            # player_row = new_row

        if keys[pygame.K_DOWN]:
            new_row += 1
            # player_row = new_row

        if keys[pygame.K_LEFT]:
            new_column -= 1
            # player_column = new_column

        if keys[pygame.K_RIGHT]:
            new_column += 1
            # player_column = new_column

        screen.fill(background_color)

        for row in range(len(maze)):
            for column in range(len(maze[0])):
                tiles = pygame.Rect(column * tile_size, row * tile_size, tile_size, tile_size)

                if maze[row][column] ==1 :
                    # pygame.draw.rect(screen, black, tiles)
                    screen.blit(background_tile,tiles)

                elif maze[row][column] == 0:
                    # pygame.draw.rect(screen, white, tiles)
                    screen.blit(path_tile, tiles)
                    pygame.draw.rect(screen, 'spring green3', tiles, 5)

                elif maze[row][column] == 10:
                    pygame.draw.rect(screen, 'salmon1', tiles)
                    pygame.draw.rect(screen, 'spring green3', tiles, 5)

                elif maze[row][column] == 20:
                    pygame.draw.rect(screen, 'blue', tiles)
                    pygame.draw.rect(screen, 'spring green3', tiles, 5)

                elif maze[row][column] == 30:
                    screen.blit(cash,(column * tile_size, row * tile_size))
                    pygame.draw.rect(screen, 'spring green3', tiles, 5)

                elif maze[row][column] == 40:
                    screen.blit(spike,(column * tile_size, row * tile_size))
                    pygame.draw.rect(screen, 'spring green3', tiles, 5)

                elif maze[row][column] == 50:
                    screen.blit(hole,(column * tile_size, row * tile_size))
                    pygame.draw.rect(screen, 'spring green3', tiles, 5)



        player_x = player_column * tile_size
        player_y = player_row * tile_size
        screen.blit(char,(player_x,player_y))

        # pygame.draw.circle(screen, 'red', (player_x, player_y), 20)
        # pygame.draw.circle(screen, 'black', (player_x, player_y), 20, 2)

        if 0 <= new_row < len(maze) and 0 <= new_column < len(maze[0]):
            if maze[new_row][new_column] == 0 or maze[new_row][new_column]==10 or maze[new_row][new_column]==20 or maze[new_row][new_column] == 30 or maze[new_row][new_column] == 40 or maze[new_row][new_column] == 50:

                if maze[new_row][new_column] == 30:
                    maze[new_row][new_column] = 0
                    score += 1
                if maze[new_row][new_column] == 40:
                    maze[new_row][new_column] = 0
                    score -= 1
                if maze[new_row][new_column] == 50:
                    new_row, new_column = 1,8

                player_row, player_column = new_row, new_column

        text_counter = font.render(f"Score: {score}", True, ("white"))
        screen.blit(text_counter, (600, 50))

        pygame.time.delay(100)
        pygame.display.flip()


    return



while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        if event.type==pygame.MOUSEBUTTONDOWN:
            if exit_button.collidepoint(event.pos):
                running=False
            if play_button.collidepoint(event.pos):
                print("play button was clicked")
                maze()


    screen.fill(background_color)

    pygame.draw.rect(screen,'green',play_button,border_radius=20)
    pygame.draw.rect(screen,'red',exit_button,border_radius=20)
    font=pygame.font.Font(None,36)

    play_text=font.render("Play",True,'black')
    exit_text=font.render("Exit",True,'black')

    screen.blit(play_text,(play_button.x+75,play_button.y+10))
    screen.blit(exit_text, (exit_button.x+75, exit_button.y+10))

    pygame.display.flip()
