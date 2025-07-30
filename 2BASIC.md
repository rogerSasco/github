# git local directory
goto project directory to initiate git $ cd E:\proj dir\proj name>
```
|___proj dir
       |___proj name
```

# git auth user
```shell
git init // initiate git in curr dir
git add . //add all files in project dir
git config --global user.email "rogergoh@sasco.org.sg"
git config --global user.name "rogerSasco"
git commit -m "version 1"   //-m means message
```

# add local repo
```shell
gh repo create REPONAME --public
git init
git remote add origin https://github.com/rogerSasco/REPONAME.git
git branch -M main
```
![addLocalRepo](/images/gitCreateRepo.png)

# git add repo steps
```shell
git add .
git commit -m "message or version"
git push origin -u main
```
![gitAdd](/images/gitAdd.png)

# clone existing repo from github
```shell
git clone https://github.com/rogerSasco/REPONAME.git
```

Once you have tried the above, goto [3BRANCHING.md](/3BRANCHING.md)
# References:
Git tutorial 1 (37min)
https://youtu.be/hrTQipWp6co?si=IWGvxzinkYimlhf7

Git tutorial 2 (57min)
https://youtu.be/1ibmWyt8hfw?si=WZaCTMmQ2Gdyw45Z

How Git Works (4min)
https://youtu.be/e9lnsKot_SQ?si=kujJov0mZxdqGb_c
