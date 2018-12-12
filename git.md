### Keep up with Upstream
```
# add original repository as 'upstream' remote if not yet added
git remote -v
git remote add upstream https://github.com/kubeflow/examples.git
# fetch latest from 'upstream'
git fetch upstream
# check current topic branch
git branch -a
# switch to correct topic branch
git checkout master
# merge main branch of 'upstream' into current topic branch
git merge upstream/master
# push changes to 'origin' remote
git push origin master
```
