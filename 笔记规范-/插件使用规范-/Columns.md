#abolish : 虽然好看,但操作并不方便

col         用来分行,间隔一行空行 则会创建一个col
col-md  空行也不会创建一个col ,主要用于放置内容

col-md-x x是数字,表示col的宽度, 取值是 0.5到10的倍数,例如 1、1.5、6.5 等

还可以 调整高度,字体对齐,弹性增长 ,不过需要用代码块的格式
	非必要统一使用>[!col]的格式


### 例子
> [!col]
>> [!info] Callouts
>> Stuff inside the callout
>> More stuff inside.
>>> [!ERROR] Error description
>>> Nested callout
>>> - example MD code
>>> - more stuff
>
>> [!col-md-2.5]
>> # Text annotation example:
>>> [!col]
>>>> [!col-md]
>>>> 1. Function name **a** should be more descriptive
>>>> 2. Remove **if/else** by using **||**
>>> 
>>>> [!col-md-2]
>>>> ```js
>>>> function a(word) {
>>>> 	if (word != null) {
>>>> 			console.log(word);
>>>> 	} else {
>>>> 		console.log("a");
>>>> 	}
>>>> }
>>>> let msg = "Hello, world!";
>>>> console.log(msg)