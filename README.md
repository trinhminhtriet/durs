# 📉 Durs

```text
     _
  __| | _   _  _ __  ___
 / _` || | | || '__|/ __|
| (_| || |_| || |   \__ \
 \__,_| \__,_||_|   |___/
```

📉 Durs: A fast, intuitive disk usage analyzer in Rust. Quickly assess file system space with efficient, clear visualizations and insights.

## Demo

![durs](media/demo.gif)

## ✨ Features

Durs quickly shows which directories are using the most disk space without needing extra commands like sort or head. If there’s a folder you don’t have permission to access, Durs will display just one message `Did not have permissions message` for it and continue scanning.

It displays the largest files or folders that can fit on your terminal screen, going deep into the file structure to find the biggest items automatically. This removes the need for `-d` or `-h` flags, keeping things simple. The largest directories are highlighted with color for easy identification.

The color bars reflect both the directory structure and disk usage, with shades of gray to show folder hierarchy. For example, if `.steam` is a large folder using 44% of space, lighter gray lines from `.steam` show subfolders inside it. This helps you see that deleting `.steam` would also remove everything inside it.

## 🚀 Installation

To install **durs**, simply clone the repository and follow the instructions below:

```bash
git clone https://github.com/trinhminhtriet/durs.git
cd durs

cargo build --release
cp ./target/release/durs /usr/local/bin/
durs --version
```

Running the below command will globally install the `durs` binary.

```bash
cargo install durs
```

## 💡 Usage

```
Usage: durs
Usage: durs <dir>
Usage: durs <dir>  <another_dir> <and_more>
Usage: durs -p (full-path - Show fullpath of the subdirectories)
Usage: durs -s (apparent-size - shows the length of the file as opposed to the amount of disk space it uses)
Usage: durs -n 30  (Shows 30 directories instead of the default [default is terminal height])
Usage: durs -d 3  (Shows 3 levels of subdirectories)
Usage: durs -D (Show only directories (eg durs -D))
Usage: durs -F (Show only files - finds your largest files)
Usage: durs -r (reverse order of output)
Usage: durs -o si/b/kb/kib/mb/mib/gb/gib (si - prints sizes in powers of 1000. Others print size in that format).
Usage: durs -X ignore  (ignore all files and directories with the name 'ignore')
Usage: durs -x (Only show directories on the same filesystem)
Usage: durs -b (Do not show percentages or draw ASCII bars)
Usage: durs -B (--bars-on-right - Percent bars moved to right side of screen)
Usage: durs -i (Do not show hidden files)
Usage: durs -c (No colors [monochrome])
Usage: durs -C (Force colors)
Usage: durs -f (Count files instead of diskspace)
Usage: durs -t (Group by filetype)
Usage: durs -z 10M (min-size, Only include files larger than 10M)
Usage: durs -e regex (Only include files matching this regex (eg durs -e "\.png$" would match png files))
Usage: durs -v regex (Exclude files matching this regex (eg durs -v "\.png$" would ignore png files))
Usage: durs -L (dereference-links - Treat sym links as directories and go into them)
Usage: durs -P (Disable the progress indicator)
Usage: durs -R (For screen readers. Removes bars/symbols. Adds new column: depth level. (May want to use -p for full path too))
Usage: durs -S (Custom Stack size - Use if you see: 'fatal runtime error: stack overflow' (default allocation: low memory=1048576, high memory=1073741824)"),
Usage: durs --skip-total (No total row will be displayed)
Usage: durs -z 40000/30MB/20kib (Exclude output files/directories below size 40000 bytes / 30MB / 20KiB)
Usage: durs -j (Prints JSON representation of directories, try: durs -j  | jq)
Usage: durs --files0-from=FILE (Reads null-terminated file paths from FILE); If FILE is - then read from stdin
```

## Config file

Durs has a config file where the above options can be set.
Either: `~/.config/durs/config.toml` or `~/.durs.toml`

```
$ cat ~/.config/durs/config.toml
reverse=true
```

## 🗑️ Uninstallation

Running the below command will globally uninstall the `durs` binary.

```bash
cargo uninstall durs
```

Remove the project repo

```bash
rm -rf /path/to/git/clone/durs
```

## 🤝 How to contribute

We welcome contributions!

- Fork this repository;
- Create a branch with your feature: `git checkout -b my-feature`;
- Commit your changes: `git commit -m "feat: my new feature"`;
- Push to your branch: `git push origin my-feature`.

Once your pull request has been merged, you can delete your branch.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
