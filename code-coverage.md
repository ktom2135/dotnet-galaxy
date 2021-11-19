## 准备工作：
1. 安装 Coverlet
   
   ```
   dotnet add package coverlet.collector

   ```

2. 运行测试

```
dotnet test --collect:"XPlat Code Coverage"

```
运行结束后， 会生成TestResult文件夹


3. 查看结果：

由于结果是xml格式， 需要转换成html格式以便查看：

3.1. 安装工具

```
dotnet tool install -g dotnet-reportgenerator-globaltool
```

3.2. 将 reportgenerator 加入到 ~/.zshrc

```
code ~/.zshrc

在文件结尾计入：
export PATH="$PATH:/Users/chenxu/.dotnet/tools"
```

3.3: 将xml转换成html:

在TestTesult文件下运行：

```
reportgenerator -reports:"coverage.cobertura.xml" -targetdir:"coveragereport" -reporttypes:Html
```

3.4: 查看coveragereport文件夹下的index.html
