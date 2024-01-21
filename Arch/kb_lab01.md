 # kb 


 ## kb1 docker-compose 在build镜像时使用代理

在构建时，可以制定参数，或者设置环境变量：

通过指定构建参数：

```bash
docker-compose build \
--build-arg http_proxy=http://proxy.exaple.com \
--build-arg https_proxy=http://proxy.exaple.com
```



通过设置环境变量：

```bash
# docker-compose.yaml
build:
  context: .
args:
  - http_proxy=http://proxy.com
  - https_proxy=http://proxy.com
```


https://cloud.tencent.com/developer/article/1806455




## Poetry

poetry 是Python 中用于依赖管理和打包的工具。它允许您声明项目所依赖的库，并将为您管理（安装/更新）它们。Poetry 提供了一个锁定文件以确保可重复安装，并且可以构建您的项目以进行分发。

作为一个传统虚拟环境的实现，poetry 凭借其强大的依赖分析能力被大量项目所推荐的虚拟环境管理工具。

对于绝大部分的开发者而言，poetry 作为首选的虚拟环境管理工具是最优方案，其强大的依赖分析能力、环境封装能力以及庞大的社区均可为你的开发保驾护航，这也是我目前最为推荐所有 python 开发者所掌握的虚拟环境管理工具。

https://www.cnblogs.com/liuzhongkun/p/16797346.html


### 区别

virtualenv, pipenv 和 poetry 是 Python 中的三个虚拟环境管理工具。

virtualenv 可以帮助你在 Python 项目中创建独立的 Python 环境，以便于在不同的项目之间隔离第三方包。这样，每个项目就可以拥有自己独立的 Python 环境，并且不会因为其他项目的包版本而导致冲突。

pipenv 是一个简化 Python 虚拟环境管理的工具。它使用较少的命令就可以创建虚拟环境、安装依赖包和管理包版本，还可以生成 Pipfile 和 Pipfile.lock 文件，用于记录项目依赖的包及版本。

poetry 是一个用于 Python 项目依赖管理和打包的工具。它可以帮助你管理项目依赖的包、版本和环境，并生成项目打包所需的文件，如 setup.py 和 pyproject.toml。

总结一下，virtualenv 是一个创建独立 Python 环境的工具，pipenv 是一个简化 Python 虚拟环境管理的工具，而 poetry 是一个用于 Python 项目依赖管理和打包的工具。




