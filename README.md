# git_collate_contributions

analyse contributions to a git repo, and produce a breakdown of commits, insertions and deletions per user


### Usage

To use it, clone this repo (e.g. to `~/git_collate_contributions`), then simply invoke from within your git repo folder:
```
$ ~/git_collate_contributions/git_collate_contributions 
AUTHOR                                           COMMITS      INSERTIONS       DELETIONS
========================================================================================
J-Donald Tournier                                   1909          377761          295731
Robert Smith                                        1486          165042           82263
Dave Raffelt                                         967          104738           73925
Max Pietsch                                          502           23157           16915
Thijs Dhollander                                     214           23191           38907
Rami Tabbara                                         179           42199           16931
Daan Christiaens                                     176           15519           15753
Ben Jeurissen                                         74            3536            1160
Daniel Blezek                                          8             543              50
Sascha Frydman                                         8             140             177
Chun-Hung Jimmy Yeh                                    5              37              16
rei19q                                                 4             316              88
Kenneth Hoste                                          4               4               4
WillBrennan                                            3             385             390
Marmaduke Woodman                                      2              49               3
Jelle Veraart                                          2              32               4
www-data                                               2               0               0
Tom Close                                              2               9              17
Pannek, Kerstin (H&B, Herston - RBWH)                  1               9              14
CanWood                                                1               1               1
rdpauw                                                 1               1               1
maedoc                                                 1               2               2
Kristian Loewe                                         1              24              58
gfagiolo                                               1              61              29
```


### Additional arguments

You can pass additional arguments to the command, which will be passed as-is to
the corresponding `git log` call. This useful to select branches or remotes,
e.g.:
```
$ ~/git_collate_contributions/git_collate_contributions --all
$ ~/git_collate_contributions/git_collate_contributions --remotes=origin
```


### Name substitutions

To handle cases where the same user has pushed commits under different names,
you can provide a list of aliases in the `substitutions` file. This file must
reside alongside the script itself for the command to find it. The format for
this file is:
```
Jane Doe: janedoe 
Joe Bloggs: jbloggs 'Joe M. Bloggs' "JM Bloggs"
```
With one line for each user. In the example above, contributions for `janedoe`
will be attributed to `Jane Doe`, etc. 

