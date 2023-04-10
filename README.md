# tic_tak
As part of my programming coursework, I created a command-line version of the classic game Tic Tac Toe using Python. The game allows two players to take turns placing their markers on a 3x3 game board, with the first player to get three in a row declared the winner.
def print_board(board):
    print(board[0], "|", board[1], "|", board[2])
    print("---------")
    print(board[3], "|", board[4], "|", board[5])
    print("---------")
    print(board[6], "|", board[7], "|", board[8])

def check_win(board):
    if board[0] == board[1] == board[2]:
        return True
    elif board[3] == board[4] == board[5]:
        return True
    elif board[6] == board[7] == board[8]:
        return True
    elif board[0] == board[3] == board[6]:
        return True
    elif board[1] == board[4] == board[7]:
        return True
    elif board[2] == board[5] == board[8]:
        return True
    elif board[0] == board[4] == board[8]:
        return True
    elif board[2] == board[4] == board[6]:
        return True
    else:
        return False

def tic_tac_toe():
    board = [1, 2, 3, 4, 5, 6, 7, 8, 9]
    player = 1
    while True:
        print_board(board)
        if check_win(board):
            print("Player", player, "wins!")
            break
        if player == 1:
            choice = int(input("Player 1, enter your move (1-9): "))
            if board[choice-1] == "X" or board[choice-1] == "O":
                print("Invalid move, try again.")
                continue
            else:
                board[choice-1] = "X"
                player = 2
        else:
            choice = int(input("Player 2, enter your move (1-9): "))
            if board[choice-1] == "X" or board[choice-1] == "O":
                print("Invalid move, try again.")
                continue
            else:
                board[choice-1] = "O"
                player = 1

tic_tac_toe()
