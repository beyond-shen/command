## clone 整个项目
```
git clone https://github.com/limingth/microduino.git
cd microduino
git branch -a
git log
```

## 切换分支
```
git checkout dev/limingth
git checkout development
git checkout master
```

## 每次切换分支后，确认所在分支的相关信息
```
git branch 
git log
```

## 拉取development最新代码到自己的分支下
```
git checkout dev/limingth
git reset --hard origin/development
git log
git branch
```

## 出现冲突
```
git rebase --skip  （可能会用到）
```

## 提交自己的新修改
```
git commit -a -m "[Maodou]: Shipping: #123, update something"
git push origin dev/limingth
```
