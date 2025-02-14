
# Project-SearchEverywhere

This is a tool that lists out all the lines containing [keyword] in the [File(s)] specified by user.

This tool I have made especially for college students so that they can easily find out the topics they wish to study from a number of ppt, pdf and document files provided by the professors. However in general it can be used by anyone.

This is a powerful tool, as whenever you need to fetch a particular information from a file or a bunch of files, you can just give it a go and get exactly what you looking for without even opening any files.

This works well with .txt, .odp, .odt, .pdf files as of now. A quick demo, showing working of this program is available [here](https://www.linkedin.com/posts/suraj-singh-5092_connections-stackoverflow-project-activity-6816378849006374912-awv_)

## Analogy

If you are familiar with ```cat``` and ```grep``` tools and have at some point of time piped your output to ```grep``` command or done piping like ```cat syslog.log | grep ERROR``` or ```cat *.txt | grep "xyz information"``` then to tell you this program basically does similar type of work, under the hood. 

As ```cat``` only works on ```plain text``` files, and can't show you the text in ```.odp```(presentations), ```.odt```(word files), ```.pdf``` files, this program does all this conversions in background to allow you to even peek in these files and get the information you are looking for.


## Difference
-> In a directory having ```plain text``` files, below both will work with same efficiency.

```bash
cat * | grep "information"
```

```bash
SearchEverywhere - "information"
```


-> But if the files are ```word documents(.odt)```, ```pdfs```, ```presentations(.odp)``` types then

```bash
cat * | grep "information"    # would NOT work
``` 

```bash
SearchEverywhere - "information"    # will still work
``` 
> The results are saved for later use in a `results.txt` file, so if in case user wants to use them, he/she may. But the file is overwritten every time a new search is performed.

> On files other than `.txt` type, conversions are done, and new directories are made. They can safely be removed after program terminates or can be utilised by user.

## Installation 

This works on Debian based as well as Arch based distros and can be installed by following these commands:

```bash 
  git clone https://github.com/suraj-singh12/Project-SearchEverywhere/
```
```bash  
  cd Project-SearchEverywhere
```
```bash
  sudo chmod +x /dist/SearchEverywhere
```
#### Install Dependencies [arch-based (eg. Fedora)]
```bash
  sudo sh fedoradep.sh
```
#### Install Dependencies [debian-based (eg. Ubuntu)]
```bash
  sudo sh debiandep.sh
```
#### Install the tool
```bash
  sudo sh install.sh
```

## Usage
To learn to use this easily, you may enter into ```testing_base``` directory, post installation of the tool.

```bash
cd testing_base
SearchEverywhere - heading    # will search 'heading' keyword in all files

SearchEverywhere -txt python  # will search 'python' keyword in all txt files
SearchEverywhere text_file.txt python # will search 'python' keyword in text_file.txt file

SearchEverywhere -odt "Final Purpose" # will search 'Final Purpose' keyword in all .odt file type files
SearchEverywhere mydocument2.odt "Final Purpose" # will search 'Final Purpose' keyword in mydocument.odt file

SearchEverywhere -odp "contains specific" # will search 'contains specific' keyword in all .odp files
SearchEverywhere mypresentation2.odp "contains specific" # will search 'contains specific' keyword in mypresentation.odp file

SearchEverywhere -pdf "member functions" # will search 'member functions' in all .pdf files
SearchEverywhere LectureNotes.pdf "member functions" # will search 'member functions' in LectureNotes.pdf files
```

An example video is given [here](https://www.linkedin.com/posts/suraj-singh-5092_connections-stackoverflow-project-activity-6816378849006374912-awv_), you may prefer to go through it incase you are facing any difficulty in learning this.

## Few Pointes
1. The search is case insensitive.
2. First time run on .odp files takes some time. The time taken is linear with the number of .odp files in the directory

## Contributing

Contributions are always welcome!
Kindly check out ```CONTRIBUTING.md```
