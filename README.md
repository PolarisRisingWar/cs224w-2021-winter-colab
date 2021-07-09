本项目是作者学习CS224W 2021冬季课程过程中完成的相应colab。因为作者太菜，很多知识都是从零学起，所以在notebook中加了很多个人的笔记、注释等内容。  
部分个人笔记组成的cell前面添加了PRW（PolarisRisingWar）注释标识以与真正的代码作为区分。  
有参考其他GitHub、和鲸社区等平台上的代码。具体参考资料在CSDN上发布课程笔记中详写。笔记合集链接：[cs224w（图机器学习）2021冬季课程学习笔记集合](https://blog.csdn.net/PolarisRisingWar/article/details/117287320)。  
由于笔记仍在更新，所以部分参考资料仍然未整理发布。如有侵犯他人正当权益之嫌，请直接联系我。  
我绝大多数内容都是在Linux服务器上跑的，所以Windows端如果要跑的话不知道会不会出现奇怪的问题。  
不保证正确性，仅供参考。如有谬误欢迎指正，作者是老GitHub常驻居民，几乎每天都能过来看看。  
如果您想要看课程notebook原件，但是由于不可控力等原因无法下载colab文件，也可以找我。如果真有人有这样需求的话，我把原文件再下一遍传到GitHub上。  

课程笔记发布在CSDN上，仍在努力更新ing。合集链接：[cs224w（图机器学习）2021冬季课程学习笔记集合](https://blog.csdn.net/PolarisRisingWar/article/details/117287320)  

2021/6/21更新：看到issue里面有人提，我就把colab所使用的数据集acm.pkl下载到根目录下了，这样就可以直接跑代码了。  
在原colab中是使用Google Drive下载的数据。为需考虑我也把代码复制过来了：
```python
from pydrive.auth import GoogleAuth
from pydrive.drive import GoogleDrive
from google.colab import auth
from oauth2client.client import GoogleCredentials

# Authenticate and create the PyDrive client
auth.authenticate_user()
gauth = GoogleAuth()
gauth.credentials = GoogleCredentials.get_application_default()
drive = GoogleDrive(gauth)
```
```python
id='1ivlxd6lJMcZ9taS44TMGG72x2V1GeVvk'
downloaded = drive.CreateFile({'id': id})
downloaded.GetContentFile('acm.pkl')
```
（顺带一提可以参考我写的[colab tutorial笔记](https://blog.csdn.net/PolarisRisingWar/article/details/117229594#t2)，也可以直接用shell命令gdown下载数据。）
<br><br><br>
2021/7/9更新colab 3:（具体内容可参考我的博客）
1. 删掉了很多个人笔记内容。
2. 将原本colab中固定的一个F.dropout加上了self.training。
3. 改了一下edge_indices_disjoint函数，我原来考虑无向边了，把相应内容删掉。
4. 修改了cora数据集存储在本地的根目录位置，都改成了/tmp/cora这个文件夹。