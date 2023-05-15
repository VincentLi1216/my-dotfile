# My Shell Setting

```shell
my-dotfile
├── vim
│   └── bundle/
├── .shellScripts
│   └── runc
├── oh-my-zsh/
└── zsh
```

## Vim

## oh-my-zsh

## Shell Scripts

### Compile c/cpp
```SHELL
#!/bin/zsh

if [[ "$1" == *.cpp ]]; then
  output="${1%.cpp}"
elif [[ "$1" == *.c ]]; then
	output="${1%.c}"
else
  output="$1"
fi

gcc "$output".c -o "$output".out 2> /dev/null || clang++ -std=c++17 -stdlib=libc++ "$output".cpp -o "$output".out 2> /dev/null

"$PWD/$output".out

exit 0
```