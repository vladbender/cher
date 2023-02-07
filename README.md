# cher

Данная утилита запускает код программ на разных языках без необходимости устанавливать компиляторы и тулинг для каждой программы.

## Использование

cher имеет 3 режима работы:
- run
- repl
- shell

В режиме **run** запускает код на выбранном языке программирования и выводит результат в консоль:
```bash
% ./cher run test_sources/main.rs
Hello from Rust! Do you know that 2^10 = 1024?
%
```

В режиме **repl** запускает REPL (read-eval-print-loop) в языках которые его имеют:
```bash
% ./cher repl ruby 
irb(main):002:0> 2**42
=> 4398046511104
% 
```

В режиме **shell** запускает терминал выбранного языка в контейнере с доступом ко всем тулам этого языка. При этом все файлы текущей директории доступны по пути `/workdir`:
```bash
% ./cher shell go
/go$ cd /workdir/test_sources/
/workdir/test_sources$ go run main.go 
Hello from Golang!
/workdir/test_sources$ 
%
```

## Установка

На Linux и MacOS:
```bash
sudo curl https://raw.githubusercontent.com/vladislavvv/cher/main/cher --output /usr/local/bin/cher
sudo chmod +x /usr/local/bin/cher
```

## Тесты

Можно запустить тесты с простейшими hello world вариантами.

**WARNING!** Будет скачано множество докер образов на каждый язык.
```bash
./test
```

## Требования

- docker

## Поддерживаемые языки

- JavaScript (Node.js)
- TypeScript (Node.js)
- Golang
- Rust
- Python
- Ruby
- Java
- C/C++
- PHP

## TODO
- Проверка что переданный файл существует и является файлом (а не, например, директорией)
- Работа с относительными и абсолютные путями. В относительных учесть пути "наверх"
- Поддержка других языков
- (?) сlean режим для удаления ненужных образов