## node.js中的path模块
  1、路径解析，对不同的操作系统得到规范化的路径格式
  
    var myPath = path.normalize(__dirname + '/test/a//b//../c/utilyou.mp3');
    console.log(myPath);    //windows: E:\workspace\NodeJS\app\fs\test\a\c\utilyou.mp3

  2、路径结合、合并，路径最后不会带目录分隔符

    path.join([path1],[path2]..[pathn]);    //[path1] 路径或表示目录的字符

    var path1 = 'path1',
        path2 = 'path2//pp\\',
        path3 = '../path3';
    var myPath = path.join(path1, path2, path3);
    console.log(myPath);    //path1\path2\path3

  3、获取绝对路径，以应用程序为起点，根据参数字符串解析出一个绝对路径

    //path.resolve(path1, [path2]..[pathn]);    //path 必须至少一个路径字符串值

    var myPath = path.resolve('path1', 'path2', 'a/b\\c/');
    console.log(myPath);    //E:\workspace\NodeJS\path1\path2\a\b\c

  4、获取相对路径,获取两路径之间的相对关系

    //path.relative(from, to);  //from 当前路径，并且方法返回值是基于from指定到to的相对路径    to  到哪路径

    var from = 'c:\\from\\a\\',
        to = 'c:/test/b';

    var _path = path.relative(from, to);
    console.log(_path); //..\..\test\b;     //表示从from到to的相对路径











参考链接：[http://nqdeng.github.io/7-days-nodejs/](http://nqdeng.github.io/7-days-nodejs/)
