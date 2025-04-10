报错：main redeclared in this block  

 原因：同一目录下有多个func main()函数的go文件

 解决：
 1.如果其它的go文件只是工具文件，不连接主函数功能，则可以忽略报错直接 `go run main.go`运行指定文件。  
 2.可以把这些func main()的文件放入不同目录，解决报错。  

 

 
