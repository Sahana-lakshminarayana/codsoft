import math

# Initialize the board
def init_board():
    return [' ' for _ in range(9)]

# Print the board
def print_board(board):
    for i in range(3):
        print('|'.join(board[i*3:(i+1)*3]))
        if i < 2:
            print('-+-+-')

# Check for winner
def check_winner(board, player):
    win_conditions = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],  # Rows
        [0, 3, 6], [1, 4, 7], [2, 5, 8],  # Columns
        [0, 4, 8], [2, 4, 6]              # Diagonals
    ]
    for condition in win_conditions:
        if all(board[i] == player for i in condition):
            return True
    return False

# Check for a draw
def check_draw(board):
    return ' ' not in board

# Minimax algorithm with Alpha-Beta Pruning
def minimax(board, depth, is_maximizing, alpha, beta):
    if check_winner(board, 'O'):
        return 1
    if check_winner(board, 'X'):
        return -1
    if check_draw(board):
        return 0

    if is_maximizing:
        max_eval = -math.inf
        for i in range(9):
            if board[i] == ' ':
                board[i] = 'O'
                eval = minimax(board, depth + 1, False, alpha, beta)
                board[i] = ' '
                max_eval = max(max_eval, eval)
                alpha = max(alpha, eval)
                if beta <= alpha:
                    break
        return max_eval
    else:
        min_eval = math.inf
        for i in range(9):
            if board[i] == ' ':
                board[i] = 'X'
                eval = minimax(board, depth + 1, True, alpha, beta)
                board[i] = ' '
                min_eval = min(min_eval, eval)
                beta = min(beta, eval)
                if beta <= alpha:
                    break
        return min_eval

# AI move
def ai_move(board):
    best_score = -math.inf
    move = -1
    for i in range(9):
        if board[i] == ' ':
            board[i] = 'O'
            score = minimax(board, 0, False, -math.inf, math.inf)
            board[i] = ' '
            if score > best_score:
                best_score = score
                move = i
    board[move] = 'O'

# Player move
def player_move(board):
    while True:
        move = int(input("Enter your move (1-9): ")) - 1
        if 0 <= move < 9 and board[move] == ' ':
            board[move] = 'X'
            break
        else:
            print("Invalid move. Try again.")

# Main function
def main():
    board = init_board()
    print("Welcome to Tic-Tac-Toe!")
    print("You are 'X' and the AI is 'O'.")
    print_board(board)

    while True:
        player_move(board)
        print_board(board)
        if check_winner(board, 'X'):
            print("You win!")
            break
        if check_draw(board):
            print("It's a draw!")
            break

        print("AI's turn...")
        ai_move(board)
        print_board(board)
        if check_winner(board, 'O'):
            print("AI wins!")
            break
        if check_draw(board):
            print("It's a draw!")
            break

if __name__ == "__main__":
    main()