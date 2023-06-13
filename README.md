import pygame
import random

# Definiera färger
SVART = (0, 0, 0)
VIT = (255, 255, 255)
CYAN = (0, 255, 255)
GUL = (255, 255, 0)
LILA = (128, 0, 128)
GRÖN = (0, 255, 0)
RÖD = (255, 0, 0)
BLÅ = (0, 0, 255)
ORANGE = (255, 165, 0)

# Definiera storlek på fönster och rutnät
RUTNÄT_STORLEK = 25
RUTNÄT_BREDD = 10
RUTNÄT_HÖJD = 20
FÖNSTER_BREDD = RUTNÄT_BREDD * RUTNÄT_STORLEK
FÖNSTER_HÖJD = RUTNÄT_HÖJD * RUTNÄT_STORLEK

# Definiera formerna för tetrominonerna
FORMER = [
    [[1, 1, 1, 1]],  # I-formen
    [[1, 1], [1, 1]],  # O-formen
    [[1, 1, 0], [0, 1, 1]],  # S-formen
    [[0, 1, 1], [1, 1, 0]],  # Z-formen
    [[1, 1, 1], [0, 1, 0]],  # L-formen
    [[1, 1, 1], [1, 0, 0]],  # J-formen
    [[1, 1, 1], [0, 0, 1]]  # T-formen
]


def skapa_rutnät():
    rutnät = [[SVART] * RUTNÄT_BREDD for _ in range(RUTNÄT_HÖJD)]
    return rutnät


def rita_rutnät(fönster, rutnät):
    for y in range(len(rutnät)):
        for x in range(len(rutnät[y])):
            pygame.draw.rect(fönster, rutnät[y][x], (x * RUTNÄT_STORLEK, y * RUTNÄT_STORLEK, RUTNÄT_STORLEK, RUTNÄT_STORLEK))
    pygame.draw.rect(fönster, VIT, (0, 0, FÖNSTER_BREDD, FÖNSTER_HÖJD), 5)


def placera_tetromino(rutnät, tetromino, position):
    for y in range(len(tetromino)):
        for x in range(len(tetromino[y])):
            if tetromino[y][x] == 1:
                rutnät[position[1] + y][position[0] + x] = tetromino_färg


def ta_bort_tetromino(rutnät, tetromino, position):
    for y in range(len(tetromino)):
        for x in range(len(tetromino[y])):
            if tetromino[y][x] == 1:
                rutnät[position[1] + y][position[0] + x]

