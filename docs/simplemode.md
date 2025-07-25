# 极简模式

见[issue69](https://github.com/Rock-Candy-Tea/hexo-circle-of-friends/issues/69)，推出极简模式。旨在最简程度运行程序，并输出最简化结果。

部署方式如下：

fork 友链朋友圈的项目仓库，地址：https://github.com/Rock-Candy-Tea/hexo-circle-of-friends

编辑`fc_settings.yaml`文件，需要修改的配置如下：

```yaml
LINK:
  - { link: "https://www.yyyzyyyz.cn/link/", theme: "butterfly" } # link改为你的友链页地址，theme选择你的博客主题
```

编辑`.github/workflows/CI.yml`文件，将`SIMPLE_MODE`设置为`true`：

```yaml
SIMPLE_MODE: true # 极简模式是否开启
```

点击你的仓库`Settings-->Actions-->General`，找到`Workflow permissions`，选择`Read and write permissions`，如图：

![actions权限修改.png](actions权限修改.png)

启用你的仓库的 github action，点击`Actions-->I understand my workflows, go ahead and enable them`

![启用actions.png](启用actions.png)

之后点击`update-friends-posts`并启用`workflow`

![QQ截图20220205081424](QQ截图20220205081424.png)

然后点击`Run workflow--->Run workflow`进行第一次运行

![image-20221008232746973](image-20221008232746973.png)

等待运行完毕后，仓库会上传`data.json`，文件内容与 api：`/all`内容相同，供用户自行取用。
