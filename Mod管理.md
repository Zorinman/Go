当导入一个新的Go项目时，在终端以次执行以下两个命令：  
如果项目里有go.mod文件和go.sum没有报错可以不用执行，如果有报错直接执行命令2,如果还报错则执行1，2    
如果没有有go.mod文件和go.sum则 执行1.2  

### 1.`go mod init <moudle name>`

作用
初始化一个新的 Go 模块（Module），生成 go.mod 文件以及go.sum

使用场景
项目首次启用 Go Modules 时（新建项目或迁移旧项目到 Modules）。

必须在项目根目录运行。

注意这里的moudl name名称必须与 代码中引用的包的前缀名称相同
如下图中的filestore-seraver，这说明之前项目都是从该go模块导入包的
所以我们创建的go模块名称为filestore-server   `go mod init filestore-server`
![image](https://github.com/user-attachments/assets/f20e631f-deef-4d6d-8845-061c124ae895)
![image](https://github.com/user-attachments/assets/a78ac5e4-7ec8-48f3-8670-e727176d8b60)



### 2.`go mod tidy`  
作用
同步项目的依赖关系：

添加代码中实际引用的依赖（自动写入 go.mod 和 go.sum）。

移除未使用的依赖（清理 go.mod）。

使用场景
代码中新增/删除了依赖项后（如复制他人代码或修改 import 语句）。

确保依赖版本与代码实际需求一致。


-----------------



###  ` go clean -modcache`  
作用
彻底清理本地模块缓存（$GOPATH/pkg/mod 下的所有依赖包）。

使用场景
依赖缓存损坏导致编译异常（如 checksum mismatch 错误）。

需要强制重新下载所有依赖（如切换代理或清理磁盘空间）。
