# AtCoder_mkdir_com
コンテストのたびにdir移動したり、mkdirしたりすんのめんどくさいから実行ファイル作った

## 実行例
`.`を打たないとカレンとシェルでcdが実行されない(http://itdoc.hitachi.co.jp/manuals/3021/3021313320/JPAS0366.HTM)

`. abc 179`


## abc
なぜファイル名がabcかと言うと、主にAtCoderBeginnerContest(ABC)に出ているためです。

```abc
#!/bin/sh

＃($1)は第一引数で、上の実行例で言うところの`179`です。
＃作りたいfile名→僕の場合は、AtCoderBeginnerContest(コンテスト番号)にしたいので以下のようにしました。
file="AtCoderBeginnerContest$1"

＃戻って、dirを作るところまでのpathを[path]のところに記入する
cd ~/
cd [path]

#引数がない場合
if [ "$1" = "" ];then 
	echo 引数がないよばーか
#[file]が既に存在してる場合は移動するだけ
elif [ -d $file ];then
	cd $file
#ない場合は作るか聞いて、作るなら作って移動
else
    echo "dirないよ。作ったろか？(y/n)"
		read ans
		if [ "$ans" = "y" ];then
			mkdir $file
			cd $file
		fi
fi
```

たったこれだけだから、誰も使わないだろうけど自分用としておいとくよ
path通すの忘れないでね。
