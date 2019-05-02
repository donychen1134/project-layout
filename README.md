# project-layout

本项目记录了 Go 目录结构的最佳实践。

想法主要来源于 [Go Project Layout](https://medium.com/golang-learn/go-project-layout-e5213cdcfaa2) 及 [project-layout](https://github.com/golang-standards/project-layout)。

## cmd

主要用来存放项目中的各种 main 文件。

当项目中有多个应用程序时，每个应用程序会有自己的 main.go 文件。可以将不同 app 的 main.go 文件放在各个 /cmd/app_name/ 目录下，结构清晰明了。

## conf

存放项目的配置文件。

conf 或 configs 均可，个人偏向简洁一点的 conf。

## internal

存放项目**私有**源代码包，/internal 目录下的代码不能被其他项目引用，但是可以在本项目内部引用。

Go 1.4 引入了 [internal packages](https://golang.org/doc/go1.4#internalpackages) 的概念。当项目中有代码不希望被别项目引用时，可以将代码放置在 /internal 目录下。

## pkg

存放项目**公共**源代码包，/pkg 目录下的代码可以作为完整的包被其他项目引用。

/pkg 目录下的文件，应该以功能完整包为单位组织。不同包中的代码应尽量独立，减少耦合，方便外部引用。

## third_party

经修改的第三方库。

项目开发中，经常需要引用第三方库。如果第三方库不满足需求时，可能会对其进行一些修改。这部分经过修改的第三方代码应放在 /third_party 目录下。

## vendor

未修改的第三方库。

项目中引用的未修改的第三方库。通常使用依赖管理工具管理，如 [govendor](https://github.com/kardianos/govendor) 或 [dep](https://github.com/golang/dep)。

## scripts

存放脚本文件。

存放安装、分析、构建等功能的脚本，如：build.sh、table.sql 等。可以使项目根目录保持整洁。