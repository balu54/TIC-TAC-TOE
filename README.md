from tkinter import *
from tkinter import messagebox

window = Tk()
window.minsize(500, 750)
window.maxsize(501, 750)
window.title("TIC TAC TOE")
window.iconbitmap("C:/Users/solob/PycharmProjects/programs/Images/tic.ico")


def allset():
    reset()
    restart()




x_win = 0
o_win = 0
tie = 0
click = True
c = 0
winneer = False


def disable():
    b1.config(state="disabled")
    b2.config(state="disabled")
    b3.config(state="disabled")
    b4.config(state="disabled")
    b5.config(state="disabled")
    b6.config(state="disabled")
    b7.config(state="disabled")
    b8.config(state="disabled")
    b9.config(state="disabled")


def restart():
    global c
    c = 0
    Buttons()


def reset():
    global x_win, o_win, tie, c
    x_win = 0
    o_win = 0
    c = 0
    tie = 0
    label()


def won():
    global c, x_win, o_win, tie
    if (b1["text"] == "X" and b2["text"] == "X" and b3["text"] == "X") or (
            b1["text"] == "O" and b2["text"] == "O" and b3["text"] == "O"):

        b1.config(bg="black", fg="white")
        b2.config(bg="black", fg="white")
        b3.config(bg="black", fg="white")
        if b1["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")

        # disable()
        # time.sleep(10)

        restart()
        c = 0


    elif (b4["text"] == "X" and b5["text"] == "X" and b6["text"] == "X") or (
            b4["text"] == "O" and b5["text"] == "O" and b6["text"] == "O"):

        b4.config(bg="black", fg="white")
        b5.config(bg="black", fg="white")
        b6.config(bg="black", fg="white")
        if b4["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        c = 0
        restart()

    elif (b7["text"] == "X" and b8["text"] == "X" and b9["text"] == "X") or (
            b7["text"] == "O" and b8["text"] == "O" and b9["text"] == "O"):

        b7.config(bg="black", fg="white")
        b8.config(bg="black", fg="white")
        b9.config(bg="black", fg="white")
        if b7["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        restart()
        c = 0

    elif (b1["text"] == "X" and b4["text"] == "X" and b7["text"] == "X") or (
            b4["text"] == "O" and b1["text"] == "O" and b7["text"] == "O"):

        b4.config(bg="black", fg="white")
        b1.config(bg="black", fg="white")
        b7.config(bg="black", fg="white")
        if b1["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        restart()
        c = 0

    elif (b2["text"] == "X" and b5["text"] == "X" and b8["text"] == "X") or (
            b2["text"] == "O" and b5["text"] == "O" and b8["text"] == "O"):

        b2.config(bg="black", fg="white")
        b5.config(bg="black", fg="white")
        b8.config(bg="black", fg="white")
        if b2["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        restart()
        c = 0

    elif (b3["text"] == "X" and b9["text"] == "X" and b6["text"] == "X") or (
            b3["text"] == "O" and b9["text"] == "O" and b6["text"] == "O"):

        b3.config(bg="black", fg="white")
        b9.config(bg="black", fg="white")
        b6.config(bg="black", fg="white")
        if b3["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        restart()
        c = 0

    elif (b1["text"] == "X" and b5["text"] == "X" and b9["text"] == "X") or (
            b5["text"] == "O" and b9["text"] == "O" and b1["text"] == "O"):

        b1.config(bg="black", fg="white")
        b9.config(bg="black", fg="white")
        b5.config(bg="black", fg="white")
        if b1["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        restart()
        c = 0

    elif (b3["text"] == "X" and b5["text"] == "X" and b7["text"] == "X") or (
            b3["text"] == "O" and b5["text"] == "O" and b7["text"] == "O"):

        b3.config(bg="black", fg="white")
        b5.config(bg="black", fg="white")
        b7.config(bg="black", fg="white")
        if b3["text"] == "X":
            x_win += 1
            messagebox.showinfo("TICTACTOE", "X is the winner")
        else:
            o_win += 1
            messagebox.showinfo("TICTACTOE", "O is the winner")
        restart()
        c = 0

    elif c == 9:
        messagebox.showinfo("TICTACTOE", "Its a Draw")
        restart()
        tie += 1
        c = 0

    label()


def clicked(b):
    global click, c
    if click == True and b["text"] == "":
        b.config(text="X", bg="red")
        c += 1
        click = False
        won()
    elif click == False and b["text"] == "":
        b.config(text="O", bg="blue")
        click = True
        c += 1
        won()
    else:
        messagebox.showinfo("TICTACTOE", "this button is already used...\n please select another")


def label():
    global x_win, o_win, tie
    l = Label(window, text="X-WINS", font=("Ariel", 20)).grid(row=3, column=0)
    ll = Label(window, text="O-WINS", font=("Ariel", 20)).grid(row=3, column=1)
    lll = Label(window, text="DRAWS", font=("Ariel", 20)).grid(row=3, column=2)
    la = Label(window, text=x_win, font=("Ariel", 15)).grid(row=4, column=0)
    lla = Label(window, text=o_win, font=("Ariel", 15)).grid(row=4, column=1)
    llla = Label(window, text=tie, font=("Ariel", 15)).grid(row=4, column=2)


def Buttons():
    global b1, b2, b3, b4, b5, b6, b7, b8, b9
    b1 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b1))
    b1.grid(row=0, column=0)
    b2 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b2))
    b2.grid(row=0, column=1)
    b3 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b3))
    b3.grid(row=0, column=2)
    b4 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b4))
    b4.grid(row=1, column=0)
    b5 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b5))
    b5.grid(row=1, column=1)
    b6 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b6))
    b6.grid(row=1, column=2)
    b7 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b7))
    b7.grid(row=2, column=0)
    b8 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b8))
    b8.grid(row=2, column=1)
    b9 = Button(window, font=("Ariel", 20), width=10, height=5, text="", command=lambda: clicked(b9))
    b9.grid(row=2, column=2)
    b_new_game = Button(window, font=("Ariel"), text="New Game", width=10, height=5, command=allset)
    b_new_game.grid(row=6, column=0)
    b_score_set = Button(window, font=("Ariel"), text="Reset Score", command=reset, width=10)
    b_score_set.grid(row=6, column=1)

    b_restart_game = Button(window, font=("Ariel"), text="Restart Game", command=restart, width=11, height=5)
    b_restart_game.grid(row=6, column=2)


label()
Buttons()

window.mainloop()
