# GDB noob note

基本命令

```bash
man gdb  #看手册

```

```bash
gcc -g ${fileName}  # 产生带有编译信息的可执行文件 
gdb ./a.out  
```


- `r`/ `run`

- `q`/ `quit`

- `b`/ `break` 打断点

  - `b #` 在第#行打断点

  - `b main` 在某一个函数入口处打断点

- `list` 查看源代码

- `info b` 查看断点信息

- `info watchpoint` 查看监视信息

- `n` / `next` 程序继续运行

- `p`/ `print` 显示某一个值

- `s` / `step` 步进某个函数

- `shell` 后加命令 例如`ls` `cat`

- `set logging on` 生成调试记录文件

- `watch ${addr}` 监视变量

## 


