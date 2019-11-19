## Answers - Background Processes Practice Exercises

### Answers

1. Start a new tmux

```bash
[username]$ tmux new -s s1
```

2. What's your working directory inside the tmux?

```bash
[usename]$ pwd
/home/username/data/practice_directory
```

3. Change to the `data/fastqc` directory

```bash
[username]$ cd data/fastqc/
```

4. Exit the tmux

Hit Ctrl + B, then d to detach the tmux. The message `[detached (from session s1)]` should print to your terminal and the commands and the green bar from the tmux should vanish and your previous commands should reappear.

5. What's your working directory now?

Notice it's not the directory you changed to inside the tmux

```bash
[username]$ pwd
/home/kkeith/data/practice_directory
```

6. Reattach the tmux

```bash
[username]$ tmux attach -t s1
```

7. Again, what's your working directory?

See, your working directory stayed the same inside the tmux. Everything you do inside the tmux is pretty independent of what you do outside the tmux.

```bash
[kkeith]$ pwd
/home/kkeith/data/practice_directory/data/fastqc
```

8. Detach the tmux and kill it

Again, hit Ctrl B + d to detach the tmux

```bash
[detached (from session s1)]
[username]$ tmux kill-session -t s1
```