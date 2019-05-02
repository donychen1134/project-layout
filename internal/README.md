## internal

存放项目**私有**源代码包，/internal 目录下的代码不能被其他项目引用，但是可以在本项目内部引用。

Go 1.4 引入了 [internal packages](https://golang.org/doc/go1.4#internalpackages) 的概念。当项目中有代码不希望被别项目引用时，可以将代码放置在 /internal 目录下。