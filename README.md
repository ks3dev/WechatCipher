# WechatCipher 
## 自动加密解密微信和QQ消息，通过xposed框架  
目前仅供测试，设置繁琐，bug也多。  
支持微信6.5.7，QQ6.7.1和7.0.0  
previews文件夹下有预览图  
  
### 注意一下可能不会随QQ微信更新而更新，过两天可能会调整检测机制，不再通过控件id而是它在界面树中的位置关系判断，应该就可以适配更多版本了。不过咱更希望你萌自己拿去修改使用~
  
### 食用方法 
1. 确保已安装xposed框架并且版本较新。  
2. 仔细阅读此软件源码以确保此插件没有监视你的通信内容或其他恶意行为，编译并安装。咱使用的是安卓上的开发环境AIDE，兼容Android Studio但是会有一些差异，比如gradle文件可能需要修改。eclipse玩家请褪裙。  
3. 在xposed中启用此插件并重启爪机(软重启好像不行)。
4. 从桌面打开此插件，先创建加密解密规则。每条规则具有名称、明文前缀、密码、加密方法、后处理(混淆)方法这些属性，你可以将不同好友使用的加密规则都添加进去，这样就可以解密他们的消息。
5. 创建完规则，再创建至少一个方案。每个方案可以指定一个加密规则和多个解密规则。加密规则用于加密你发送的消息，而解密规则用于尝试不同的规则来解密来自不同好友的消息。注意，解密规则里至少应该包括你的加密规则，否则你无法正常看到自己发送的消息。 
最简单的设置方法是所有人都用同一个规则，这意味着你只需要创建一个规则和一个方案。 
  
### 不能保证安全
1. 配置文件可以被任何软件读取(好像也只能设置成这样，不然插件自己从QQ微信的UID也没法获取配置文件了)。密文存储也没什么用，因为其他应用同样可以读取本插件的apk和so文件进行逆向来获取密钥  
2. 使用固定的前缀可能使本来安全的加密算法不再安全(不太懂这方面)  
3. 如果你通过QQ将加密规则告知他人，那加密对于QQ和有关部门将变的透明，只能起规避敏感词防止自动审查的作用了  
如果你因为信任此插件被查水表了，咱只能表示幸灾乐祸了噗哈哈  

### 缺陷  
1. 上述安全问题1  
2. 修改某加密解密规则的名称或将其删除后，使用该规则的方案将无法使用，打开其设置界面将崩溃  
3. 会将一些无关内容识别为Toolbar标题  
4. 这玩意根本就没卵用好不好…(这才是重点)  

### 欢迎借鉴和抄袭  
做这个东西只是想玩玩xposed以及提供一个idea，在这个隐私被严重无视的时代需要更多人真正为用户考虑。对于一个正常的企业不管用户是什么人都应该保护他们的信息，在任何问题上保持中立。而腾讯显然没有做到。  
欢迎参照这个制作PC版，安卓免xposed版(参考方块启动器，或利用安卓无障碍服务)，苹果版(通过subtract还是啥)。WP玩家请褪裙。  
转载严禁注明出处，注意看清楚，是严禁注明出处。欢迎转载。  
表层网络真是不安全啊。  
你也可以用这个来学习xposed模块的编写。我觉的注释写的挺多了。  
 
### 当你使用此软件或阅读源码意味着同意以下原则:  
0. 我赞同新世界秩序  
1. 我相信互联网应该是一个自发、自治的社区  
2. 我支持信息的自由流通，也希望这个世界更自由开放  
3. 我支持知识产权保护，但是反对将其用作谋求暴利的手段；对于唯利是图者，破解其作品是正义的  
4. 我不会将技术用于作恶  
  
不同意也没关系。我们不会像某些邪恶组织一样非要强加一些东西给别人。 
