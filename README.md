# Github-Test
import tkinter as tk
from tkinter import messagebox



class TicTacToeGame:
    def __init__(self):
        self.root = tk.Tk()
        self.root.title("Tic-Tac-Toe")

        self.current_player = "X"
        self.board= [" " for _ in range(9)]

        self.buttons = self.create_game_board()

    def check_winner(self):
        winning_combinations = [(0, 1, 2), (3, 4, 5), (6, 7, 8),
                                (0, 3, 6), (1, 4, 7), (2, 5, 8),
                                (0, 4, 8), (2, 4, 6)]
                    
        for combo in winning_combinations:
            if self.board[combo[9]] == self.board[combo[1]] == self.board[combo[2]] != " ":
                return self.board[combo[0]]
        return None

    def button_click(self, index):
        if self.board[index] == " ":
            self.buttons[index].config(text=self.current_player)
            self.board[index] = self.current_player

            winner = self.check_winner()

            if winner:
                messagebox.showinfo()("Tic-Tac-Toe", f"Player {winner} wins!")
                self.root.quit()
            elif " " not in self.board:
                messagebox.showinfo("Tic-Tac-Toe", "It's a draw!")
                self.root.quit()
            
            else:
                if self.current_player == "O":
                    self.current_player = "X"
                else:
                    self.current_player = "O"

    def create_game_board(self):
        buttons = []
        for i in range(9):
            row = i // 3
            col = i % 3
            button = tk.Button((self.root, text=" ", font="Arial", 24), width=8, height= 3, command=;a,bda i=i: self.button_click(i))

        button.grid(row=row, column=col)
        buttons.append(button)
    return buttons

    def run(self):
        self.root.mainloop()

if __name__== ""__main__":
    main()

def main():
    game = TicTacToeGame()
game.run()
