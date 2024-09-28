:::color2
代码仓库地址： [https://gitee.com/shuiruohanyu/wechat_02](https://gitee.com/shuiruohanyu/wechat_02)

:::

:::color2
接下来，我们通过一个综合性的大案例来实现微信聊天功能，里面涉及音视频处理-照相机处理-和常规的一些操作

:::

![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1708400191768-004e418e-df30-40a7-996c-7d04c868875a.gif)

<h1 id="jbVhS">创建一个wechat项目</h1>
![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707399175439-1b6a2cec-e637-4532-ba19-a4d44dfd4d34.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_56%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
使用API12的编辑器需要更新依赖

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711781429319-db422dbc-2a9c-4225-b7a9-5a365c9347be.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_24%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::

:::color2
将讲义中的图片添加到resources/base/media目录下

[图片.zip](https://weiqi123.yuque.com/attachments/yuque/0/2024/zip/32778948/1727514411340-ed32bd8f-e810-44f6-a2e7-39a5f35f5455.zip)

:::

+ 拷贝所有图片 

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707399227379-ad437bcb-c766-4f29-ba13-0971cd030d2a.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_31%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



+ 导入所有基本色值到color.json中

```typescript
{
  "color": [
    {
      "name": "start_window_background",
      "value": "#FFFFFF"
    },
    {
      "name": "primary",
      "value": "#1AAD19"
    },
    {
      "name": "second_primary",
      "value": "#a9ea7a"
    },
    {
      "name": "text_primary",
      "value": "#2A2929"
    },
    {
      "name": "text_second",
      "value": "#818181"
    },
    {
      "name": "back_color",
      "value": "#ededed"
    },
    {
      "name": "second_back_color",
      "value": "#f6f6f6"
    },
    {
      "name": "border_color",
      "value": "#f4f5f6"
    },
    {
      "name": "danger",
      "value": "#e75f58"
    },
    {
      "name": "white",
      "value": "#ffffff"
    },
    {
      "name": "bottom_color",
      "value": "#a4a4a4"
    },
    {
      "name": "bottom_voice_color",
      "value": "#515151"
    },
    {
      "name": "voice_back_color",
      "value": "#CC3E3E3E"
    },
    {
      "name": "voice_round_color",
      "value": "#323232"
    },
    {
      "name": "voice_round_font_color",
      "value": "#919191"
    },
    {
      "name": "chat_primary",
      "value": "#8aec71"
    },
    {
      "name": "animate_voice_color",
      "value": "#4a8040"
    },
    {
      "name": "black",
      "value": "#000000"
    },
    {
      "name": "popup_back",
      "value": "#4d4d4d"
    },
    {
      "name": "location_back",
      "value": "#80767676"
    },
    {
      "name": "pay_back",
      "value": "#57ab70"
    }
  ]
}
```

+ 修改项目的名称

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707401810937-f152a884-1ff1-432b-be23-cb0ab65d6500.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_34%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
如果你也想修改英文环境下的，可以同时修改

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707401854840-78469bc7-bdb3-4592-828a-201bf933fc6f.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_33%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::

+ 使用API12的编辑器来生成图标

:::color2
![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711782191689-13cbcee3-28b2-4ee2-bd48-fcccfc84b10b.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_18%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

最终选用最大的图标替换media目录下的foreground.png

:::



+ 使用git管理

:::color2
建立一个仓库，使用git管理该项目

:::

+ 在项目目录下执行

```bash
$ git init 
```

+ 通过DevEcoStudio自带的git进行提交和推送

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707401579166-e08b2d21-21c4-43a6-bd57-585528eee4d5.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_20%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

<h1 id="YthHA">搭建基础骨架页面</h1>
![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707401903671-ee2bcf8f-cf66-4023-9d49-54d19738a673.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color2
首先实现主页中四个基本的tab组件，并且能够实现切换时样式的变化

:::

+ 在ets/models目录下新建一个tab.ets文件

```typescript
// tabs图标
export class TabBarClass {
  title: string = ""
  name: string = ""
  icon: ResourceStr = ""
  selectIcon: ResourceStr = ""
}
```

+ 入口文件 pages/Index.ets

:::color2
定义四个tabbar数据

:::

```typescript
import { TabBarClass } from '../models/tab'

@State
  tabList: TabBarClass[] = [{
    icon: $r('app.media.ic_public_message'),
    name: 'wechat',
    title: '微信',
    selectIcon: $r('app.media.ic_public_message_filled')
  }, {
    icon: $r('app.media.ic_public_contacts_group'),
    name: 'connect',
    title: '联系人',
    selectIcon:  $r('app.media.ic_public_contacts_group_filled')
  }, {
    icon: $r('app.media.ic_gallery_discover'),
    name: 'discover',
    title: '发现',
    selectIcon: $r('app.media.ic_gallery_discover_filled')
  }, {
    icon: $r('app.media.ic_public_contacts'),
    name: 'my',
    title: '我的',
    selectIcon: $r('app.media.ic_public_contacts_filled')
  }]
```

+ 根据数据动态声明四个tab

```typescript
  @State
  currentIndex: number = 0
  @Builder
  CommonTabBar (item: TabBarClass) {
    Column () {
      Image(this.tabList[this.currentIndex].name === item.name ? item.selectIcon : item.icon )
        .width(20)
        .height(20)
      Text(item.title)
        .fontSize(12)
        .fontColor(item.name === this.tabList[this.currentIndex].name  ? $r('app.color.primary') : $r('app.color.text_primary'))
        .margin({
          top: 5
        })
    }
  }
build() {
    Tabs({ index: $$this.currentIndex }) {
      ForEach(this.tabList, (item: TabBarClass) => {
        TabContent() {
          Text(item.title)
        }.tabBar(this.CommonTabBar(item))

      }, (item: TabBarClass) => item.name.toString())
    }.barPosition(BarPosition.End)
    .animationDuration(300)
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707411927336-b0986ab2-e0d7-4364-a2d2-1a5554adba45.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_19%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color2
提交代码

:::



<h1 id="ly1OE">联系人数据渲染</h1>
+ 在models下新建users.ets，分别定义用户类型和10个随机数据

```typescript
// 用户信息
export interface  UserInfo {
  username: string  // 用户昵称
  avatar: string  // 用户头像
  user_id: string  // 用户id
}
export class UserInfoModel implements UserInfo {
  username: string = ''
  avatar: string = ''
  user_id: string = ''

  constructor(model: UserInfo) {
    this.username = model.username
    this.avatar = model.avatar
    this.user_id = model.user_id
  }
}
export const DefaultUserList: UserInfo[] = [{
  username: '小趴菜',
  avatar: 'https://img2.baidu.com/it/u=2778471297,524433918&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500',
  user_id: '1'
},{
  username: '老板',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2F9853de1a-3985-42e6-be59-849853318793%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069489&t=f960a72e50a399ddec92b18b3c7fc2d9',
  user_id: '2'
},{
  username: '老婆',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Fd064be90-6b8c-4a6d-9721-837206fbb4a7%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069489&t=c810057a56c27b5747e1e92bfde37799',
  user_id: '3'
},{
  username: '物业小张',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Fabf9e746-a09c-4b08-bcba-1e347a370226%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069489&t=b47c00cad15f8dbdc390e82b95348ed2',
  user_id: '4'
},{
  username: '水若寒宇',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Ff1d11ab1-35ff-4f2c-b9e9-3e0c996d34a2%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069489&t=e3234db982e8a36639d170fc5cec7848',
  user_id: '5'
},{
  username: '小林',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Fe9543d7c-02f3-484f-a3f0-5bfa8b2e6ef9%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069502&t=118303a29ce4a8ef2c1a496ae880b76b',
  user_id: '6'
},{
  username: '花开富贵',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2F8d90d041-784a-407f-a82e-b851fafdf746%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069547&t=d374ebb6973f68b95ba345827a304455',
  user_id: '7'
},{
  username: '妈妈',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2F373c6d24-1f8b-4000-8dd9-8d8410c35e71%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069618&t=51805a82420593c2a3cda47b9f65a80e',
  user_id: '8'
},{
  username: '沧海一生笑',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Fbb560b27-a0b7-4062-ae40-efe4e5a8a748%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069619&t=8605f8477712cf9c5a1159db0cd7dab4',
  user_id: '9'
},{
  username: '爱哭的燕子🐨🐨',
  avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Fdc2617f6-4a68-4d4a-8c54-8cbc84e3446a%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1708069619&t=a8b7b4f1e600d53e5547479d947b1809',
  user_id: '10'
}]
```

:::color1
这里用i2c生成了class的实现类，目的是后面的地方会使用

:::

+ 封装关于微信聊天的首选项类
+ 在ets目录下新建一个constants/index.ets 用于存储一些常量

```typescript
export const WeChat_StoreKey: string = 'wechat'  // 微信聊天存储首选项的key
export const WeChat_ConnectKey: string = 'wechat_connect' // 微信联系人的key

```

:::color2
该变量用于存储首选项的一些常用的key

:::

+ 在utils目录下新建一个chat_store.ets文件，用于存储首选项

```typescript
import { WeChat_StoreKey } from  '../constants'
import preferences from '@ohos.data.preferences'

export class WeChatStore {
  static  getWeChatStore () {
    return  preferences.getPreferences(getContext(), WeChat_StoreKey)
  }
}
```

+ 封装一个获取联系人的方法

```typescript
  // 获取微信联系人
  static async getWeChatConnect() {
    const store = await WeChatStore.getWeChatStore()
    return JSON.parse(store.getSync(WeChat_ConnectKey, JSON.stringify(DefaultUserList)) as string) as UserInfoModel[]
  }
```

+ 新建一个Connect组件，位置位于ets/pages/connect/Connect.ets

```typescript
@Component
struct Connect {
  build() {
    Text("联系人组件")
  }
}
export default Connect
```

+ 在ForEach循环中渲染该组件

```typescript
build() {
    Tabs({ index: $$this.currentIndex }) {
      ForEach(this.tabList, (item: TabBarClass) => {
        TabContent() {
          if(item.name === "connect") {
            Connect()
          }else {
            Text(item.title)
          }
        }.tabBar(this.CommonTabBar(item))

      }, (item: TabBarClass) => item.name.toString())
    }.barPosition(BarPosition.End)
    .animationDuration(300)
  }
```

+ 在Connect的初始化中获取员工数据

```typescript
import { promptAction } from '@kit.ArkUI'
import { UserInfo, UserInfoModel } from '../../models/users'
import { WeChatStore } from '../../utils/chat_store'

@Component
struct Connect {
  @State
  userList: UserInfoModel[] = []

  aboutToAppear(): void {
    this.getUserList()
  }

  async getUserList() {
    this.userList = await WeChatStore.getWeChatConnect()
  }

  build() {
    Text(JSON.stringify(this.userList))
  }
}

export default Connect
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707413420403-f6489e80-34dd-4538-a05e-94e5cfb7d279.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color3
需要模拟器or真机才可以看到数据

:::

+ 完成基本的结构渲染- Connect/Index.ets

```typescript
 build() {
    Column() {
      Row() {
        Search({ placeholder: '搜索' })
          .height(30)
          .backgroundColor($r('app.color.white'))
          .borderRadius(4)
      }.width('100%')
      .padding({
        left: 10,
        right: 10
      })

      List () {
        ForEach(this.userList, (item: UserInfo) => {
          ListItem() {
            Row({ space: 10 }) {
              Image(item.avatar)
                .width(30)
                .height(30)
                .borderRadius(4)
              Column() {
                Text(item.username)
                  .fontColor($r('app.color.text_primary'))
                  .fontSize(14)
              }.layoutWeight(1)
              .alignItems(HorizontalAlign.Start)
              .justifyContent(FlexAlign.Center)
            }
            .width('100%')
            .height(60)
            .padding({ left: 10, right: 10 })
            .stateStyles({
              pressed: {
                .backgroundColor($r('app.color.back_color'))
              },
              normal: {
                .backgroundColor($r('app.color.white'))
              }
            })
          }
        }, (item: UserInfo) => item.user_id)
      }
      .backgroundColor(Color.White)
      .padding({
        top: 10,
        bottom: 10
      })
      .divider({
        strokeWidth: 1,
        color: $r('app.color.border_color')
      })
    }
    .height('100%')
    .padding({
      top: 20
    })
    .backgroundColor($r('app.color.back_color'))
  }
```



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707447642918-f768381b-8aa8-49d4-9f45-a716438f345a.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_16%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color3
请注意，因为图片中用到了在线图片，需要在module.json5中开启网络权限

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707447688237-5a16d5ce-d112-495d-a906-edb982e5831d.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_41%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::



<h1 id="w32vZ">联系人筛选</h1>
+ 定义一个筛选字段和筛选后的数组

```typescript
 @State
  searchName: string = ""
  @State
  filterList: UserInfoModel[] = []
```

+ 绑定搜索输入框

```typescript
 Search({ placeholder: '搜索', value: $$this.searchName })
```

+ 实现更新方法

```typescript
 updateFilterList () {
    if(this.searchName) {
      this.filterList = this.userList.filter(item => item.username.indexOf(this.searchName) > -1)
      return
    }
    this.filterList = this.userList
  }
```

+ 在获取完用户之后更新一次

```typescript
async getUserList() {
    this.userList = await WeChatStore.getWeChatConnect()
    this.updateFilterList()
  }
```

+ 监听searchName的变化-执行该方法

```typescript
 @State
  @Watch("updateFilterList")
  searchName: string = ""
```

+ 替换循环的内容

```typescript
  ForEach(this.filterList, (item: UserInfoModel) => {
```

+ 效果

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708399786929-b2bbf3b0-45b9-4c61-912d-18252418072e.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::info
提交代码

:::

<h1 id="LlFU7">新建聊天详情页面</h1>
:::color3
当点击联系人里面的任何一个人的时候，我们需要进入和当前人的聊天详情-聊天详情应该是个页面

:::

+ 新建pages/ChatDetail/ChatDetail.ets文件

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707447964587-9bca78bf-8f2c-4875-b157-92256040e809.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_70%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

```typescript
@Entry
@Component
struct ChatDetail {
  build() {
    Column() {
      Row() {
        Stack({ alignContent: Alignment.Start }) {
          Image($r('app.media.ic_public_arrow_left'))
            .width(30)
            .height(30)

          Text("小果果")
            .width('100%')
            .textAlign(TextAlign.Center)
            .fontSize(16)
            .fontColor($r('app.color.text_primary'))
        }
        .height(50)
      }
      .padding({
        left: 10,
        right: 10
      })
    }
  }
}
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707494860442-e30ad46f-cc63-492a-8c11-958a23406446.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_18%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 点击任意的用户跳转到聊天详情

:::color3
在Connect/Index.ets中注册点击事件

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707495349127-18a1ddd4-abff-47db-8bb0-2b437fd4817f.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_38%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 点击聊天页返回路由

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707495487681-382d29ea-0b11-43e8-934f-4557754528f8.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_43%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color3
这里由于用了Stack堆叠容器，导致之前的图片组件被后添加的文本盖住了 所以需要调整一下层级

:::



:::color1
提交代码

:::



<h1 id="xHWPz">建立默认用户</h1>
:::color1
由于当前获取当前用户的接口，我们在首选项中定义一个默认的用户

:::

```typescript
// 当前默认用户
export const CurrentUser: UserInfo = {
  username: '老高',
  avatar: 'https://img2.baidu.com/it/u=3135824442,872902204&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500',
  user_id: '9999'
}
```

+ 在常量中定义一个key

```typescript
export const WeChat_CurrentUserKey: string = "wechat_current_user" // 当前用户信息
```

+ 在首选项中定义一个获取当前用户的方法

```typescript
// 获取当前用户信息
  static async getCurrentUser()  {
    const store = await WeChatStore.getWeChatStore()
    return JSON.parse(store.getSync(WeChat_CurrentUserKey, JSON.stringify(CurrentUser)) as string) as UserInfoModel
  }
```

+ 在ability启动之后获取当前用户并设置给全局状态

```typescript
async onWindowStageCreate(windowStage: window.WindowStage): Promise<void>  {
    // Main window is created, set main page for this ability
    hilog.info(0x0000, 'testTag', '%{public}s', 'Ability onWindowStageCreate');
    WeChatStore.context = this.context
    const user = await WeChatStore.getCurrentUser()
    AppStorage.setOrCreate<UserInfoModel>(WeChat_CurrentUserKey, user)
    windowStage.loadContent('pages/Index', async (err) => {
      if (err.code) {
        hilog.error(0x0000, 'testTag', 'Failed to load the content. Cause: %{public}s', JSON.stringify(err) ?? '');
        return;
      }
      hilog.info(0x0000, 'testTag', 'Succeeded in loading the content.');
    });
  }

```

:::success
注意： 在ability中调用的方法中如果用到了getContext，此时是拿不到内容的，所以我们需要对原来的首选项管理进行一些调整

:::

+ 首选项调整

```typescript
static context: Context
  static getWeChatStore() {
    return preferences.getPreferences(WeChatStore.context || getContext(), WeChat_StoreKey)
  }
```

+ 在聊天详情中初始化时获取当前用户的数据

```typescript
@StorageProp(WeChat_CurrentUserKey)
currentUser: UserInfoModel = new UserInfoModel({} as UserInfo)
```



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707496079834-c4b4c342-7884-4e46-ac26-f22d5ac7adaf.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



<h1 id="QfMVz">点击联系人传入通信用户</h1>
:::color1
当点击某个联系人进行聊天时，要将该联系人的信息传入到聊天详情中

:::

+ Connect/Index.ets

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707496217790-19853b57-5d40-4b7e-88e2-9ad6572f05e2.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_32%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 在聊天详情中接收参数

```typescript
@Provide
  talkUser: UserInfoModel = new UserInfoModel({} as UserInfo)
  aboutToAppear(): void {
     this.getTalkUser()
  }
  // 获取聊天者信息
  async getTalkUser () {
    this.talkUser = router.getParams() as UserInfoModel
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711532128799-db3056d6-4a48-4c4d-98f4-259add7d21ca.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_49%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 将头部的信息换成实时的聊天人信息

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707525316406-feb05527-3224-401b-93cc-e64aa7ce1974.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_41%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color1
提交代码

:::



<h1 id="JuEVm">封装底部输入框组件</h1>
![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707543371230-3f15786e-913a-498e-a715-d43ce7824348.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
新建一个组件- ChatDetail/Components/BottomInput.ets

:::

```typescript
@Preview
@Component
struct BottomInput {
  build() {
    Column() {
      Row({ space: 10 }) {
        Image($r('app.media.ic_public_sound'))
          .width(25)
          .height(25)

        TextInput()
          .height(35)
          .layoutWeight(1)
          .borderRadius(2)
          .backgroundColor(Color.White)
        Image($r('app.media.ic_public_add_norm'))
          .width(25)
          .height(25)
      }
      .height(60)
      .width('100%')
      .padding({
        left: 10,
        right: 10
      })
    }
    .backgroundColor($r('app.color.second_back_color'))
  }
}

export default BottomInput
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707544509239-0456ae8c-fd5b-4d39-899e-382d356d1103.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_23%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 在ChatDetail中使用

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707544587504-65ba21ad-97fd-4d36-abb5-f9d3f580f072.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711532757525-7ea0710b-4d6d-46a0-ab17-d31d724387ee.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_38%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



<h1 id="YXQnA">实现键盘避让模式</h1>
:::success
在整个微信聊天项目中，我们都需要让键盘弹起时，能够将页面进行压缩

:::

+ 在ability初始化中实现键盘避让

```typescript
  const win = await windowStage.getMainWindow()
    win.getUIContext().setKeyboardAvoidMode(KeyboardAvoidMode.RESIZE)
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711533059706-f33d6948-5bb3-460c-9191-82d7470e2f3a.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_63%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::success
提交代码

:::

<h1 id="laPMW">切换输入模式</h1>
+ ChatDetail/Component/BottomInput.ets

:::color1
当点击左侧喇叭图标时，切换到语音模式，反之切换回来

:::

+ 定义一个状态控制

```typescript
 @State
 showVoice: boolean = false // 是否发送语音
```

+ 根据状态控制图标并切换

```typescript
Image(this.showVoice ? $r('app.media.ic_public_keyboard') : $r('app.media.ic_public_sound'))
          .width(25)
          .height(25)
          .onClick(() => {
            this.showVoice = !this.showVoice
          })
```

+ 根据状态控制发送语音的按钮和输入框

```typescript
    if (this.showVoice) {
          Button("按住 说话", { type: ButtonType.Normal })
            .backgroundColor(Color.White)
            .layoutWeight(1)
            .borderRadius(2)
            .fontColor($r('app.color.text_primary'))
        } else {
          TextInput()
            .height(35)
            .layoutWeight(1)
            .borderRadius(2)
            .backgroundColor(Color.White)
        }
```

![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1707546563636-fe462bba-3081-49da-9511-82a2807fef53.gif)





<h1 id="U9MC9">消息对象的创建</h1>
:::color1
不论是文本-语音-还是照片-视频，都需要消息对象类型

:::

+ 新建models/message.ets文件，创建关于消息的类型
+ 创建一个消息类型的枚举

```typescript
export enum  MessageTypeEnum {
  TEXT, // 文本
  IMAGE, // 图片
  AUDIO, // 音频
  VIDEO, // 视频
  LOCATION, // 定位
  LINK // 链接
}
```

+ 创建消息的类型

```typescript
export interface MessageInfo {
  id: string // 标识
  sendUser: UserInfo // 这条消息的发送者
  connectUser: UserInfo // 这条消息的归属者
  messageContent: string // 消息内容  文本消息  [图片] [语音‘7]
  sendTime: number // 发送时间
  // 消息类型
  messageType: MessageTypeEnum // 消息类型
  sourceFilePath: string // 音频地址 图片地址 视频地址
  sourceDuration: number // 音频或者视频的长度 单位s
}

```

+ 利用i2c来生成对应的class类型

```typescript
$ i2c ./message.ets
```

+ 生成如下代码

```typescript
export class MessageInfoModel implements MessageInfo {
  id: string = ''
  sendUser: UserInfo = new UserInfoModel({} as UserInfo)
  connectUser: UserInfo = new UserInfoModel({} as UserInfo)
  messageContent: string = ''
  sendTime: number = 0
  messageType: MessageTypeEnum = MessageTypeEnum.TEXT
  sourceFilePath: string = ''
  sourceDuration: number = 0

  constructor(model: MessageInfo) {
    this.id = model.id || util.generateRandomUUID() // 生成uuid
    this.sendUser = model.sendUser
    this.connectUser = model.connectUser
    this.messageContent = model.messageContent
    this.sendTime = model.sendTime || Date.now() // 发送时间
    this.messageType = model.messageType || MessageTypeEnum.TEXT
    this.sourceFilePath = model.sourceFilePath
    this.sourceDuration = model.sourceDuration
  }

```

:::color1
这里的id我们特殊处理下，当没有传入id时，直接在构造函数中自动生成ID

发送时间也处理下，没有传入的情况下 用当前时间

:::

<h1 id="ZR4og">创建消息组件</h1>
:::color1
在消息详情中，我们需要展示一条条的消息，此时我们新建一个Message.ets，用于展示消息内容

:::

+ 新建ChatDetail/Components/Message.ets组件

```typescript
@Preview
@Component
struct Message {
  build() {
    Row() {
      Image("https://img2.baidu.com/it/u=2778471297,524433918&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500")
        .height(40)
        .width(40)
        .borderRadius(6)
      Row() {
        Column() {
          Text("你真的很让我伤心")
            .backgroundColor($r('app.color.second_primary'))
            .fontColor($r('app.color.text_primary'))
            .padding(10)
            .lineHeight(24)
            .margin({
              left: 10,
              right: 10
            })
            .borderRadius(5)
        }

      }.layoutWeight(6)
      .justifyContent(FlexAlign.End)
      Text().layoutWeight(1)
    }
    .width('100%')
    .padding({
      left: 20,
      right: 20
    })
    .alignItems(VerticalAlign.Top)
    .direction(Direction.Rtl)
  }
}

export default Message
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707580000643-2dd3cec2-58ee-437f-8a33-cf2135b0210c.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_22%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 根据是否是自己发出的消息进行布局调整

```typescript
import { WeChat_CurrentUserKey } from '../../../constants'
import { MessageInfo, MessageInfoModel } from '../../../models/message'
import { UserInfo, UserInfoModel } from '../../../models/users'

@Preview
@Component
struct Message {
  @StorageProp(WeChat_CurrentUserKey)
  currentUser: UserInfoModel = new UserInfoModel({} as UserInfo)
  @Prop
  currentMessage: MessageInfoModel = new MessageInfoModel({} as MessageInfo)
  @State
  isOwnMessage: boolean = this.currentUser.user_id === this.currentMessage?.sendUser?.user_id
  build() {
    Row() {
      Image("https://img2.baidu.com/it/u=2778471297,524433918&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500")
        .height(40)
        .width(40)
        .borderRadius(6)
      Row() {
        Column() {
          Text("你真的很让我伤心")
            .backgroundColor(this.isOwnMessage ? $r('app.color.second_primary') : $r('app.color.white'))
            .fontColor($r('app.color.text_primary'))
            .padding(10)
            .lineHeight(24)
            .margin({
              left: 10,
              right: 10
            })
            .borderRadius(5)
        }

      }.layoutWeight(6)
      .justifyContent(this.isOwnMessage ? FlexAlign.End : FlexAlign.Start)
      Text().layoutWeight(1)
    }
    .width('100%')
    .padding({
      left: 20,
      right: 20
    })
    .alignItems(VerticalAlign.Top)
    .direction(this.isOwnMessage ? Direction.Rtl : Direction.Ltr)
  }
}

export default Message
```

+ 在ChatDetail中测试几个消息

```typescript
 // 放置消息组件
      List({  space: 20 }) {
        ForEach([1,2,3,4,5,6,7,8,9,10,11,12], () => {
          ListItem() {
            Message()
          }
        })
      }
      .layoutWeight(1)
      .width('100%')
      .padding({
        top: 20,
        bottom: 70
      })
      .backgroundColor($r('app.color.back_color'))

```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707617802136-9f17039c-d403-44bc-810a-3c01708aba0e.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_23%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color1
提交代码

:::

<h1 id="sAnLh">输入消息，将作者的消息更新到消息列表</h1>
:::color1
+ 双向绑定输入框内容
+ 输入内容点击发送时，将信息传入到父组件
+ 父组件拿到消息添加到当前列表中

:::

+ 双向绑定输入框内容-ChatDetail/Components/BottomInput.ets

```typescript
  @State
  content: string = "" // 输入内容
  sendTextMessage: (content: string) => void = () => {} // 发送消息

```

+ 使用$$双向绑定

```typescript
TextInput({ text: $$this.content  })
```

+ 监听onSubmit事件

```typescript
 TextInput({ text: $$this.content  })
  ...
.onSubmit(() => {
              if(this.content) {
                   this.sendTextMessage(this.content)
                   this.content = "" // 设置为空
                }
            })
```

+ 在ChatDetail中定义一个列表

```typescript
  @State
  messList: MessageInfoModel[] = []
```

+ 循环列表

```typescript
 // 放置消息组件
      List({  space: 20 }) {
        ForEach(this.messList, (item: MessageInfoModel) => {
          ListItem() {
            Message({ currentMessage: item })
          }
        })
      }
```

+ 在父组件中定义一个方法，传递给BottomInput组件

```typescript
     //  放置底部组件
      BottomInput({
        sendTextMessage: (content: string) => {
          this.sendTextMessage(content)
        }
      })
```

+ 添加sendTextMessage的方法

```typescript
// 发送文本消息
  sendTextMessage(content: string) {
    let message = new MessageInfoModel({
      messageContent: content,
      sendUser: this.currentUser,
      connectUser: this.talkUser,
    } as MessageInfo)
    this.messList.push(message) // 添加到信息的底部
  }
```

+ 将信息内容换成动态的![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711538134373-9d596de2-4c1a-4d56-bd0f-60ed63f170da.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_66%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707667847324-a9bc6f9c-4ca6-4a45-8acc-171f2fa2e7c3.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_10%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::

<h1 id="yXGOT">封装机器人回复的请求接口</h1>
:::color1
由于我们需要对话，我们可以利用一个机器人聊天的接口来获取对应的数据响应

接口地址：[https://api.ownthink.com/bot?appid=xiaosi&userid=user&spoken=](https://api.ownthink.com/bot?appid=xiaosi&userid=user&spoken=)测试

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707668017271-8e9b7719-e82d-47bd-afbf-8d6e10119fa8.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_16%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::

+ 在models中定义一个chat.ets

```typescript
export interface ChatResponse {
  message: string,
  data: ChatData
}
export interface ChatData {
  type: number,
  info: ChatInfo
}
export interface ChatInfo {
  text: string
}
```

+ 在utils下新建一个request.ets文件，封装一个获取聊天的结果的方法

```typescript
import { ChatResponse } from '../models/chat'
import http from '@ohos.net.http';
const req = http.createHttp()

export async function requestMessage(content: string) {
  try {
    const res = await req.request(`https://api.ownthink.com/bot?appid=xiaosi&userid=user&spoken=${encodeURIComponent(content)}`)
    const result =JSON.parse(res.result as string) as ChatResponse
    return result
  } catch (error) {
    return Promise.reject(error)
  }
}
```

+ 在发送自己消息后，请求服务器获取响应的消息添加到List中

```typescript
 // 发送文本消息
 async sendTextMessage(content: string) {
    let message = new MessageInfoModel({
      messageContent: content,
      sendUser: this.currentUser,
      connectUser: this.talkUser,
    } as MessageInfo)
    this.messList.push(message) // 添加到信息的底部
    await this.getResponseMessage(content)
  }
// 获取响应消息
  async getResponseMessage (content: string) {
   const result = await requestMessage(content)
    let message = new MessageInfoModel({
      messageContent: result.data?.info?.text,
      sendUser: this.talkUser,
      connectUser: this.talkUser,
    } as MessageInfo)
    this.messList.push(message) // 添加到信息的底部
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707669857718-88f6ae1f-a454-4c61-ae48-cf96dbbed563.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



+ 当正在响应时，显示对方正在输入

```typescript
  @State
  talkUserInputIng: boolean = false // 对方正在输入  
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711807304720-4203ba5a-f47b-4e2e-baac-6cfa5cc2d2d8.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_41%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 根据状态显示对方正在输入

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707670078567-e2c77746-7671-4a44-8bc7-4fd5f4867620.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_67%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::



<h1 id="eOHmN">添加信息滚动到底部</h1>
:::color1
给List组件绑定一个scroller，每次添加信息之后，滚动到最底部就可以

:::

+ 定义一个scroller

```typescript
  // 滚动条对象
  scroller: Scroller = new Scroller()
```

+ 绑定到消息列表的列表

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707670251630-6071db51-52d8-4738-afc3-90d749d691d9.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_55%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 每次添加之后，滚动到最底部![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711807334604-94c515b2-0f47-4a37-95f3-4a5488a746a8.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_54%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)





![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707670379266-f4c0ce69-04bd-4903-b4e9-f642e0ca36a8.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color1
提交代码

:::

<h1 id="toNqh">通过首选项缓存当前的聊天记录</h1>
:::color1
每个人的聊天记录要保留

+ 每个人的聊天记录是单独存储的- 也就是每个人和"我"的聊天记录的key是不同的
+ 聊天记录要随时更新-新增-删除
+ 进入和某个人的聊天记录要读取之前的聊天记录

:::

+ 在constants/index.ets中添加一个key

```typescript
export const WeChat_UserRecordKey: string = "wechat_user_record" // 用户聊天记录
```

+ 在chat_store.ets中（利用固定Key +  对话用户id作为标识）创建 获取某个人整个的聊天记录，删除某个人整个的聊天记录，添加某个人的某一条的聊天记录，删除某个人的某一条的聊天记录

```typescript
// 获取某个人的整个的聊天记录
  static async getWeChatMessage(userId: string) {
    const store = await WeChatStore.getWeChatStore()
    return JSON.parse(store.getSync(`${WeChat_UserRecordKey}_${userId}`, "[]") as string) as MessageInfoModel[]
  }
  // 删除某个人整个的聊天记录
  static async delWeChatMessage (userId: string) {
    const store = await WeChatStore.getWeChatStore()
    store.deleteSync(`${WeChat_UserRecordKey}_${userId}`)
    await store.flush() // 更新磁盘
  }
  // 添加某个人的一条聊天记录
  static async addOneWeChatMessage(userId: string, mess: MessageInfoModel) {
    const store = await WeChatStore.getWeChatStore()
    const list = await WeChatStore.getWeChatMessage(userId)
    list.push(mess) // 添加记录
    store.putSync(`${WeChat_UserRecordKey}_${userId}`, JSON.stringify(list))
    await store.flush()
  }
  // 删除某个人的一条聊天记录
  static async delOneWeChatMessage(userId: string, messId: string) {
    const store = await WeChatStore.getWeChatStore()
    let list = await WeChatStore.getWeChatMessage(userId)
    list = list.filter(item => item.id !== messId) // 排除记录
    store.putSync(`${WeChat_UserRecordKey}_${userId}`, JSON.stringify(list))
    await store.flush()
  }
```

+ 添加记录时，存入首选项![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711807374054-41269985-bf54-4c67-90ef-a754e046ebfc.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_61%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



+ 初始化时，获取聊天记录

:::color1
我们需要在具备自己的信息和对方信息之后，才去获取聊天记录

:::

```typescript
 async getAllRecord () {
    this.messList = await WeChatStore.getWeChatMessage(this.talkUser.user_id)
    this.scroller.scrollEdge(Edge.Bottom)
  }
  // 获取聊天者信息
  async getTalkUser() {
    this.talkUser = router.getParams() as UserInfoModel
    this.getAllRecord()
  }
```



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707673419838-cfffa0e4-8f65-48b5-a688-610531b6ea24.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::



<h1 id="VG6hR">在主页建立聊天记录</h1>
:::color1
因为我们和某个人聊了天，在主页中，应该保留当前的聊天记录，聊天记录中应该是聊天的最后一条记录

:::

:::color3
只要存在聊天记录，再次进入主页时，应该获取所有人的聊天记录的最后一条

:::

+ 在utils/chat_store.ets中声明一个获取所有聊天记录的方法

```typescript
 // 获取所有人的聊天记录的最后一条
  static async getAllLastRecord () {
    const store = await WeChatStore.getWeChatStore()
    const result = store.getAllSync()
    AlertDialog.show({
      message: JSON.stringify(result)
    })
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707751982979-2db374a0-17e9-4736-a1cc-5dfac30a4405.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)'

+ 遍历找到所有的聊天记录并取出所有聊天记录，

```typescript
// 获取所有人的聊天记录的最后一条
  static async getAllLastRecord() {
    const store = await WeChatStore.getWeChatStore()
    const result = store.getAllSync() as object
    let list: MessageInfoModel[] = []
    Object.keys(result).map(key => {
      if (key.includes(WeChat_UserRecordKey)) {
        // 如果包含记录的key
        if (result[key]) {
          let recordList = JSON.parse(result[key]) as MessageInfoModel[]
          if(recordList.length) {
            // 添加最后一条记录
            list.push(recordList[recordList.length - 1])
          }
        }
      }
    })
    // 对list进行排序
    list.sort((a: MessageInfoModel, b: MessageInfoModel) => {
      return b.sendTime - a.sendTime
    })
    return list
  }
```

+ 在pages/WeChat/WeChat.ets建立主页的组件（非Page）

:::color3
初始化时，获取聊天记录

:::

```typescript
import { MessageInfoModel } from '../../models/message'
import { WeChatStore } from '../../utils/chat_store'

@Component
struct WeChat {
  @State
  list: MessageInfoModel[] = []
  aboutToAppear(): void {
    this.getRecordList()
  }
  async getRecordList () {
    this.list = await WeChatStore.getAllLastRecord()
  }
  // 转化时间
  transTime(time: number) {
    const dateObj = new Date(time)
    const year = dateObj.getFullYear()
    const month = dateObj.getMonth()
    const date = dateObj.getDate()
    const hours = dateObj.getHours();
    const minutes = dateObj.getMinutes();
    if (date === new Date().getDate()) {
      // 当天的消息
      return `${hours.toString().padStart(2, "0")}:${minutes.toString().padStart(2, "0")}`
    } else if (year === new Date().getFullYear()) {
      return `${(month + 1).toString()}月${date}日`
    } else {
      return `${year}年${(month + 1).toString()}月${date}日`
    }
  }

  build() {
    Column() {
      List() {
        ForEach(this.list, (item: MessageInfoModel) => {
          ListItem() {
            Row({ space: 10 }) {
              Image(item.connectUser.avatar)
                .width(50)
                .height(50)
                .borderRadius(4)

              Column({ space: 10 }) {
                Row() {
                  Text(item.connectUser.username)
                    .fontColor($r('app.color.text_primary'))
                    .fontSize(16)
                  Text(this.transTime(item.sendTime))
                    .fontSize(12)
                    .fontColor($r('app.color.text_second'))
                    .margin({
                      top: 10
                    })
                }
                .justifyContent(FlexAlign.SpaceBetween)
                .width('100%')

                Text(item.messageContent)
                  .fontColor($r('app.color.text_second'))
                  .fontSize(14)
                  .maxLines(1)
              }
              .justifyContent(FlexAlign.SpaceBetween)
              .alignItems(HorizontalAlign.Start)
              .height(50)
              .layoutWeight(1)
              .padding({
                top: 3,
                bottom: 3
              })
            }
            .stateStyles({
              normal: {
                .backgroundColor($r('app.color.white'))
              },
              pressed: {
                .backgroundColor($r('app.color.back_color'))
              }
            })
          }
          .padding({
            top: 10,
            bottom: 10
          })
        })
      }
      .divider({
        strokeWidth: 1,
        color: $r('app.color.border_color')
      })
      .padding({
        left: 10,
        right: 20
      })
    }

    .height('100%')


  }
}

export default WeChat
```

+ 在pages/Index.ets中显示WeChat

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711544304295-3ca57b53-af59-4870-b853-a8c8abb0d4eb.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_35%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707756164461-8e2e6b08-9bf0-4e67-aafd-ff0927698ef3.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color3
提交代码

:::



<h1 id="mjhi8">处理首选项的长度限制问题</h1>
:::color2
因为目前是将一个人所有的聊天记录存于一个Key里面，但是value的长度有8192字节的限制，

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712212993659-4f86afcb-b0b0-433d-9b66-a1043fc09e44.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_29%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::

+ 所以针对该业务进行如下的改动

:::color2
我和每个人的聊天记录存一个仓库，每条消息存单独的一个节点，一个节点的限制1万个字

+ 聊天记录仓库key规范-  固定key_+用户id
+ 聊天详情key_ 采用消息id 

:::

+ 改造后方法(调用方不需要改变)

```typescript
import {
  WeChat_StoreKey,
  WeChat_ConnectKey,
  WeChat_CurrentUserKey,
  WeChat_UserRecordKey,
} from '../constants'
import preferences from '@ohos.data.preferences'
import { DefaultUserList, UserInfoModel, CurrentUser } from '../models/users'
import { MessageInfoModel } from '../models/message'
import { emitter } from '@kit.BasicServicesKit'

export class WeChatStore {
  static context: Context

  static getWeChatStore() {
    return preferences.getPreferences(WeChatStore.context || getContext(), WeChat_StoreKey)
  }

  // 获取微信联系人
  static async getWeChatConnect() {
    const store = await WeChatStore.getWeChatStore()
    return JSON.parse(store.getSync(WeChat_ConnectKey, JSON.stringify(DefaultUserList)) as string) as UserInfoModel[]
  }

  // 获取当前用户信息
  static async getCurrentUser() {
    const store = await WeChatStore.getWeChatStore()
    return JSON.parse(store.getSync(WeChat_CurrentUserKey, JSON.stringify(CurrentUser)) as string) as UserInfoModel
  }

  static getWeChatMessageStore(userId: string) {
    return preferences.getPreferencesSync(getContext(), {
      name: `${WeChat_UserRecordKey}_${userId}`
    })
  }

  // 获取某个人的整个的聊天记录
  static  getWeChatMessage(userId: string) {
    const store = WeChatStore.getWeChatMessageStore(userId)
    const allRecord = store.getAllSync() as object
    if(allRecord) {
     const list = Object.values(allRecord).map((item: string) => JSON.parse(item) as MessageInfoModel)
      list.sort((a, b) => a.sendTime - b.sendTime )
      return list
    }
    return []

  }

  // 删除某个人整个的聊天记录
  static async delWeChatMessage(userId: string) {
    preferences.deletePreferences(getContext(), {
      name: `${WeChat_UserRecordKey}_${userId}`
    })
  }

  // 添加某个人的一条聊天记录
  static async addOneWeChatMessage(userId: string, mess: MessageInfoModel) {
    const store =  WeChatStore.getWeChatMessageStore(userId)
    store.putSync(mess.id, JSON.stringify(mess))
    await store.flush()
  }

  // 删除某个人的一条聊天记录
  static async delOneWeChatMessage(userId: string, messId: string) {
    const store =  WeChatStore.getWeChatMessageStore(userId)
    store.deleteSync(messId)
    await store.flush()
  }

  // 获取所有人的聊天记录的最后一条
  static async getAllLastRecord() {
    const users = await WeChatStore.getWeChatConnect()
    let list: MessageInfoModel[] = []
    users.forEach(user => {
      const messList = WeChatStore.getWeChatMessage(user.user_id)
      if(messList && messList.length) {
        list.push(messList[messList.length - 1])
      }
    })

    // 对list进行排序
    list.sort((a: MessageInfoModel, b: MessageInfoModel) => {
      return b.sendTime - a.sendTime
    })
    return list
  }
}
```



:::color2
处理进去详情页不滚动到底部的问题

:::



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712215661369-8a56a29e-cb12-4d3f-953a-948c8fc53ea4.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_47%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

<h1 id="SaTJ0">通过线程通信更新聊天记录</h1>
:::info
emitter可以支持不同线程内的数据通信

+ 用法
1. <font style="color:rgb(40, 113, 204);">通过on方法监听事件</font>
2. <font style="color:rgb(40, 113, 204);">通过emit触发事件</font>
3. <font style="color:rgb(40, 113, 204);">需要通过统一的eventId或者eventName来绑定来进行绑定</font>

:::



:::color2
因为无论怎么发消息，都会讲过chat_store中的添加消息和删除消息，所以只需要在这里出发事件即可

:::

+ 在constants/index.ets中定义一个更新聊天记录事件名称

```typescript
export const Record_Update_EventName: string = "update_record" // 更新聊天记录的key
```

+ 在添加或者删除消息的时候，触发该事件

```typescript
// 添加某个人的一条聊天记录
  static async addOneWeChatMessage(userId: string, mess: MessageInfoModel) {
    const store = await WeChatStore.getWeChatStore()
    const list = await WeChatStore.getWeChatMessage(userId)
    list.push(mess) // 添加记录
    store.putSync(`${WeChat_UserRecordKey}_${userId}`, JSON.stringify(list))
    await store.flush()
    emitter.emit(Record_Update_EventName)
  }

  // 删除某个人的一条聊天记录
  static async delOneWeChatMessage(userId: string, messId: string) {
    const store = await WeChatStore.getWeChatStore()
    let list = await WeChatStore.getWeChatMessage(userId)
    list = list.filter(item => item.id !== messId) // 排除记录
    store.putSync(`${WeChat_UserRecordKey}_${userId}`, JSON.stringify(list))
    await store.flush()
    emitter.emit(Record_Update_EventName)
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707757118037-bfaca0e5-b499-47a1-91ad-8c93a56f2909.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_61%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 在WeChat/Index.ets中监听

```typescript
 async getRecordList () {
    this.list = await WeChatStore.getAllLastRecord()
    emitter.on(Record_Update_EventName, async () => {
      // 更新聊天记录
      this.list = await WeChatStore.getAllLastRecord()
    })
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711692746533-98394895-06d0-4895-a473-b9ea45dec583.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_16%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color2
提交代码

:::



<h1 id="KQdci">点击主页的聊天进入聊天详情</h1>
:::color2
当我们点击主页的聊天记录时，我们需要进入到详情中

+ 和之前点击联系人进入聊天详情一致

:::

+ 注册ListItem的点击事件

```typescript
ListItem() 
...
  .onClick(() => {
             router.pushUrl({
              url: 'pages/ChatDetail/ChatDetail',
              params: item.connectUser
            })
          })
```

![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1707759291176-01be5c49-b28e-49df-9027-69128f6f88f9.gif)



:::color1
提交代码

:::



<h1 id="gLFXQ">聊天详情-长按显示浮层菜单</h1>
:::color1
+ 根据微信的交互，当我们长按一个信息的时候，应该会出现如图

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707790144281-2ac7eafa-aaa6-43f9-8480-2a032771d5b9.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_21%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 所以我们需要根据手势事件 + 状态控制来显示这些

:::

+ 定义一个显示Popup的状态

:::success
组件位置： ChatDetail/Components/Message.ets

:::

```typescript
  @State
  showPopup: boolean = false // 是否显示浮层
```

+ 给每个文本消息绑定长按手势事件

```typescript
Column() {
  ...
}
.gesture(
          LongPressGesture()
            .onAction(() => {
              this.showPopup = true // 显示父层
            }))
```

+ 给当前的文本元素使用bindPopup属性

```typescript
 Text(this.currentMessage.messageContent)
          .backgroundColor(this.isOwnMessage ? $r("app.color.second_primary") : $r("app.color.white"))
          .fontColor($r("app.color.text_primary"))
          .padding(10)
          .margin({
            left: 10,
            right: 10
          })
          .borderRadius(4)
          .bindPopup(this.showPopup, {
            builder:  this.getContent,
            popupColor: $r("app.color.popup_back"),
            backgroundBlurStyle: BlurStyle.NONE,
            onStateChange: (event) => {
              // 当手指点了其他位置 关闭状态
              this.showPopup = event.isVisible
            }
          })
```

+ 在models/popup.ets中定义对应的类型

```typescript
export interface PopupItem {
  title: string
  icon: ResourceStr
  itemClick?: () => void
}
```

+ 在Message中声明对应的数据

```typescript
@State
  popupList: PopupItem[] = [{
    title: '听筒播放',
    icon: $r("app.media.ic_public_ears")
  },
    {
      title: '收藏',
      icon: $r("app.media.ic_public_cube")
    }, {
      title: '转文字',
      icon: $r("app.media.ic_public_trans_text")
    }, {
      title: '删除',
      icon: $r("app.media.ic_public_cancel")
    }, {
      title: '多选',
      icon: $r("app.media.ic_public_multi_select")
    }, {
      title: '引用',
      icon: $r("app.media.ic_public_link")
    }, {
      title: '提醒',
      icon: $r("app.media.ic_public_warin")
    }]
```

+ 封装getContent的builder方法

```typescript
// 用来显示弹层的内容
  @Builder
  getContent() {
     GridRow ({ columns: 5 }) {
       ForEach(this.popupList, (item: PopupItem) => {
         GridCol() {
           Column({ space: 6 }) {
             Image(item.icon)
               .fillColor($r("app.color.white"))
               .width(18)
               .height(18)
             Text(item.title)
               .fontColor($r("app.color.white"))
               .fontSize(14)
           }
           .height(60)
         }
         .onClick(() => {
           item.itemClick && item.itemClick() // 如果点击事件存在 就触发
         })
       })
     }
    .width(300)
    .padding({
      top: 15,
      left: 10
    })
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707812329399-19795026-091c-494b-842c-d1e14cf3a0e1.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color1
提交代码

:::



<h1 id="Ne3Y7">删除某一条聊天记录</h1>
+ 注册删除图标的事件

```typescript
{
      title: '删除',
      icon: $r("app.media.ic_public_cancel"),
      itemClick: () => {
         this.delMessage(this.currentMessage.id)
      }
    }
```

+ 给元素注册点击事件

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707814145374-03156483-cd7c-48b4-a1c3-fab188415a69.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_45%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 定义传入的一个方法

```typescript
// 删除信息的方法
  delMessage: (messId: string) => void = () => {}
```

+ 在父组件ChatDetail/ChatDetail.ets中传入delMessage方法

```typescript
// 删除信息的方法
  delMessage (messId: string) {
    if(messId) {
      // 先移除当前组件的数据
      const index = this.messList.findIndex(item => item.id === messId)
      if(index > -1) {
        this.messList.splice(index, 1)
      }
      // 再移除首选项的数据
      WeChatStore.delOneWeChatMessage(this.talkUser.user_id, messId)
    }
  }
```

+ 传入方法

```typescript
 Message({ currentMessage: item, delMessage: (messId: string) => {
              this.delMessage(messId)
            } })
```

![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1707814299103-c904ab4f-f7df-4920-8253-feecc1c8f7dd.gif)



:::color1
提交代码

:::



<h1 id="iwGB7">实现删除整个的聊天记录</h1>
:::color1
当我们在聊天记录中滑动某个人的聊天记录时，可以在右侧出现删除按钮，点击删除，我们就可以将整个的记录清除掉

:::

+ 来到WeChat/Index.ets文件中，在ListItem尾部添加删除元素

```typescript
ListItem() 
  ...
.swipeAction({
            end: () => {
              this.getListEnd()
            }
          })
```

+ 实现getListEnd方法

```typescript
 @Builder
  getListEnd() {
    Row() {
      Text("删除")
        .fontColor($r('app.color.white'))
        .width(100)
        .textAlign(TextAlign.Center)
    }.height(70)
    .padding({
      left: 20,
      right: 20
    })
    .backgroundColor($r('app.color.danger'))
  }
```

效果如图

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707816143669-102ec9f3-f520-4811-bd24-d17e95e33b87.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



+ 注册点击事件

```typescript
@Builder
  getListEnd(userId: string) {
    Row() {
      Text("删除")
        .fontColor($r('app.color.white'))
        .width(100)
        .height(70)
        .textAlign(TextAlign.Center)
        .onClick(() => {
           if(userId) {
             // 先删除组件中数据
             let index = this.list.findIndex(item => item.connectUser.user_id === userId)
             if(index > -1) {
               this.list.splice(index, 1)
             }
             // 再移除首选项
             WeChatStore.delWeChatMessage(userId)
           }
        })
    }.height(70)
    .padding({
      left: 20,
      right: 20
    })
    .backgroundColor($r('app.color.danger'))

  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707818975908-be6ba0b3-d0b2-4c5a-b93b-9b3b7b694f32.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_40%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::

<h1 id="dxwwd">长按显示语音组件</h1>
:::color1
现在我们基本上实现了文本消息的增删改查，接下来，我们要实现在长按“按住说话”时的语音输入组件

:::

+ 首先还是通过长按手势事件来控制
+ 监听按住说话的长按手势事件

```typescript
  @State
  showVoiceCom: boolean = false // 是否显示发送语音组件
  Button("按住 说话", { type: ButtonType.Normal })
            .backgroundColor(Color.White)
            .layoutWeight(1)
            .borderRadius(2)
            .fontColor($r('app.color.text_primary'))
           .gesture(LongPressGesture()
              .onAction(() => {
                this.showVoiceCom = true // 长按打开
              })
              .onActionEnd(() => {
                this.showVoiceCom = false // 松手关闭
              }))
```

+ 创建ChatDetail/Components/VoiceInput.ets组件

```typescript
@Component
struct VoiceInput {
  build() {
    Stack({ alignContent: Alignment.Bottom }) {
      Column() {
        // 显示关闭和文本
        Row() {
          Row() {
            Image($r("app.media.ic_public_cancel"))
              .width(30)
              .height(30)
              .fillColor($r("app.color.voice_round_font_color"))
          }
          .width(70)
          .aspectRatio(1)
          .borderRadius(35)
          .justifyContent(FlexAlign.Center)
          .backgroundColor($r("app.color.voice_round_color"))
          .rotate({
            angle: -10
          })

          Row() {
            Text("文")
              .fontSize(24)
              .textAlign(TextAlign.Center)
              .fontColor($r("app.color.voice_round_font_color"))
          }
          .width(70)
          .aspectRatio(1)
          .borderRadius(35)
          .justifyContent(FlexAlign.Center)
          .backgroundColor($r("app.color.voice_round_color"))
          .rotate({
            angle: 10
          })
        }
        .width('100%')
        .justifyContent(FlexAlign.SpaceBetween)
        .padding({
          left: 40,
          right: 40
        })
        .margin({
          bottom: 30
        })

        Stack() {
          Image($r("app.media.ic_public_output"))
            .width('100%')
            .height(120)
            .fillColor($r("app.color.bottom_color"))
            .scale({
              x: 1.2
            })
          Image($r("app.media.ic_public_recorder"))
            .width(30)
            .height(30)
            .fillColor($r("app.color.bottom_voice_color"))
        }
        .width('100%')
      }
    }
    .height('100%')
    .backgroundColor($r("app.color.voice_back_color"))

  }
}

export default VoiceInput
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707838500180-7eeeafe8-1ad7-4c72-9b98-d60e7bf051f5.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_23%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 使用bindContentConver模态控制![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711698933544-74519815-7210-4886-9534-664b1a5f4011.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_46%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

```typescript
 .bindContentCover($$this.showVoiceCom, this.getVoiceCom,{
      modalTransition: ModalTransition.NONE
    })
```



![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1707841929989-c9585a1a-908e-4ea9-b369-1f2c3e31b7e0.gif)



:::color1
提交代码

:::



<h1 id="eKQak">组合手势移动设置不同状态</h1>
:::color1
当我们长按之后，此时可以滑动左移，右移， 也可以保持留在原地，此时会有三种状态

1. 左移取消
2. 右移语音转文字
3. 留在原地录制音频

:::

+ 在models/voice.ets中导出一个枚举

```typescript
export enum VoiceRecordEnum {
  Cancel, // 取消录制
  RecordIng, // 录制中
  Transfer // 语音转化
}
```

+ 在BottomInput中声明一个初始化状态

```typescript
  @Provide
  voiceState: VoiceRecordEnum = VoiceRecordEnum.RecordIng // 当前的状态
  screenWidth: number = 0 // 记录整体宽度
```

+ 通过display获取屏幕实际宽度vp

```typescript
 aboutToAppear(): void {
    this.getScreenWidth()
  }
  async getScreenWidth() {
    const result = await display.getAllDisplays()
    if (result && result.length) {
      this.screenWidth = px2vp(result[0].width)
      this.screenHeight = px2vp(result[0].height)
    }
  }
```

+ 使用组合手势处理 长按 + 移动的业务

```typescript
 Button("按住 说话", { type: ButtonType.Normal })
  ...
  .gesture(
              GestureGroup(GestureMode.Parallel,
                // 长按手势
                LongPressGesture()
                  .onAction(() => {
                    this.showVoiceCom = true
                  })
                  .onActionEnd(() => {
                    this.showVoiceCom = false
                      this.voiceState = VoiceRecordEnum.RecordIng
                  }),
                // 拖动手势
                PanGesture()
                  .onActionUpdate((event) => {
                    // 取消
                    if (event.fingerList[0].globalY > this.screenHeight - 120) {
                      // 表示没有出去录音区
                      this.voiceState = VoiceRecordEnum.RecordIng
                    } else {
                      // 表示出去了
                      if (event.fingerList[0].globalX < this.screenWidth / 2) {
                        this.voiceState = VoiceRecordEnum.Cancel
                      } else {
                        this.voiceState = VoiceRecordEnum.Transfer
                      }
                    }

                  })
              )
            )
```

:::color1
GestureMode的属性介绍

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1707842816553-9eb7bb44-b430-4a80-a0cf-a67bd5e57a38.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_46%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

 

:::

+ 在VoiceInput中根据状态控制显示内容

```typescript
import { VoiceRecordEnum } from '../../../models/voice'

@Preview
@Component
struct VoiceInput {
  @Consume
  voiceState: VoiceRecordEnum
  aboutToDisappear(): void {
    this.voiceState = VoiceRecordEnum.RecordIng
  }
  build() {
    Stack({ alignContent: Alignment.Bottom }) {
      Column() {
      }.height('100%')
      .width('100%')
      .justifyContent(FlexAlign.Center)

      // 底部内容
      Column() {
        Row() {
          // 左侧内容
          Row() {
            Image($r('app.media.ic_public_cancel'))
              .width(30)
              .height(30)
              .fillColor(this.voiceState === VoiceRecordEnum.Cancel ? $r('app.color.text_primary') : $r('app.color.voice_round_font_color'))

          }
          .backgroundColor( this.voiceState === VoiceRecordEnum.Cancel ? $r('app.color.bottom_color') : $r('app.color.voice_round_color'))
          .width(70)
          .height(70)
          .borderRadius(35)
          .justifyContent(FlexAlign.Center)
          .rotate({
            angle: -10
          })
          .scale({
            x: this.voiceState === VoiceRecordEnum.Cancel ? 1.2 : 1,
            y: this.voiceState === VoiceRecordEnum.Cancel ? 1.2 : 1
          })

          Row() {
            Text("文")
              .textAlign(TextAlign.Center)
              .fontSize(24)
              .fontColor(this.voiceState === VoiceRecordEnum.Transfer ? $r('app.color.text_primary') : $r('app.color.voice_round_font_color'))
          }
          .backgroundColor( this.voiceState === VoiceRecordEnum.Transfer ? $r('app.color.bottom_color') : $r('app.color.voice_round_color'))
          .width(70)
          .height(70)
          .borderRadius(35)
          .justifyContent(FlexAlign.Center)
          .rotate({
            angle: 10
          })
          .scale({
            x: this.voiceState === VoiceRecordEnum.Transfer ? 1.2 : 1,
            y: this.voiceState === VoiceRecordEnum.Transfer ? 1.2 : 1
          })
        }
        .width('100%')
        .justifyContent(FlexAlign.SpaceBetween)
        .padding({
          left: 40,
          right: 40
        })
        .margin({
          bottom: 30
        })
        Stack() {
          // 底部图片
          Image($r('app.media.ic_public_output'))
            .width('100%')
            .height(120)
            .fillColor(this.voiceState === VoiceRecordEnum.RecordIng ? $r('app.color.bottom_color') : $r('app.color.voice_round_color'))
            .scale({
              x: 1.2
            })
          Image($r('app.media.ic_public_recorder'))
            .width(30)
            .height(30)
            .fillColor(this.voiceState === VoiceRecordEnum.RecordIng ? $r('app.color.bottom_voice_color') : $r('app.color.bottom_color'))

        }
        .height(120)
        .width('100%')
      }
    }
    .height('100%')
    .width('100%')
    .backgroundColor($r('app.color.voice_back_color'))
  }
}
export default VoiceInput
```

![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1707843783640-c9a48714-a3c0-4390-a94e-3e644117d382.gif)

:::color1
提交代码

:::



<h1 id="Lq2Bc">根据不同状态显示不同内容</h1>
:::color1
滑动到不同的状态时，切换显示内容的不同内容

:::

![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1707997394258-0957d754-3f42-48bb-a62e-db6a53590cb4.gif)

  

+ 封装一个builder

```typescript
 @Builder
  getDisplayContent () {
    if(this.voiceState === VoiceRecordEnum.Cancel) {
      Row()
        .height(80)
        .width(100)
        .borderRadius(20)
        .backgroundColor($r('app.color.danger'))
        .margin({
          left: 30
        })
    }
    if(this.voiceState === VoiceRecordEnum.RecordIng) {
      Row()
        .height(80)
        .width(180)
        .borderRadius(20)
        .backgroundColor($r('app.color.chat_primary'))
    }

    if(this.voiceState === VoiceRecordEnum.Transfer) {
      Row()
        .height(120)
        .width(280)
        .borderRadius(20)
        .backgroundColor($r('app.color.chat_primary'))
    }
  }
```

+ 显示内容

```typescript
 Column() {
        this.getDisplayContent()
      }.height('100%')
      .width('100%')
      .justifyContent(FlexAlign.Center)
      .alignItems(this.voiceState === VoiceRecordEnum.Cancel ?  HorizontalAlign.Start : HorizontalAlign.Center)
```

:::color1
提交代码

:::



<h1 id="OfXqn">录音实现过程、</h1>
:::color2
发送语音

   和发送消息是一样的，只不过消息的本质上是音频文件，mp3, wav, m4a,

 微信的发送语音原理- 在本地通过手机侧录制一段音频，形成 文件（写入磁盘）-buffer（内存形式）- 流

聊天记录只要存在

    微信聊天记录 存于首选项里面- 沙箱文件路径-指定的就是 音频 视频 照片 

:::





:::color2
<font style="color:rgba(0, 0, 0, 0.9);">使用AudioCapturer录制音频涉及到AudioCapturer实例的创建、音频采集参数的配置、采集的开始与停止、资源的释放等</font>

:::

:::color3
目前只支持真机测试

:::

:::success
使用Audio

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711701005307-392b6432-2a51-4a17-bbe4-c677b699de31.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_18%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711816787944-3b4a8e13-3ad9-4220-a09f-5fcdc8629d35.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_13%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
权限  麦克风 照相机 这些权限只会申请一次 就记住啦

:::

+ 首先在module.json5中配置权限申请麦克风权限

```typescript
{
      "name": "ohos.permission.MICROPHONE",
      "reason": "$string:MICROPHONE_REASON",
      "usedScene": {
        "abilities": ["EntryAbility"],
        "when": "always"
      }
    }
```



+ 在media/string.json中配置对应的reason属性

```typescript
 {
      "name": "MICROPHONE_REASON",
      "value": "用于发送语音"
    }
```

:::color2
权限分两个

    系统权限 . system_agent .  比如网络权限-不需要手动申请，不需要用户同意

    需要用户授权的权限 user_agent 。麦克风-读写通讯录 必须得用户同意

:::

+ 在长按的逻辑中判断用户是否已经申请了麦克风权限，如果没有则申请

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711704136130-f4ef22db-0077-4f8b-bfad-0466a4148fcb.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_29%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
项目一启动就申请一下 麦克风

ability的onCreate中就可以实现

:::

+ 在ability中申请麦克风权限

```typescript
 async onCreate(want: Want, launchParam: AbilityConstant.LaunchParam): Promise<void> {
    hilog.info(0x0000, 'testTag', '%{public}s', 'Ability onCreate');
    const manager = abilityAccessCtrl.createAtManager() // 创建程序控制管理器
    await manager.requestPermissionsFromUser(this.context,
      [
        "ohos.permission.MICROPHONE"
      ])
  }
```

:::color2
**<font style="color:#DF2A3F;">如果已经申请过权限，再次去请求权限弹窗已经不出来啦！！！！</font>**

**<font style="color:#DF2A3F;">当我们按住说话时，都得去检查一下</font>**

:::



:::color2
需要CheckAceessTokenSync方法来获取是否拥有了权限

但是CheckAceessTokenSync 需要tokenId, tokenId又需要 一个方法来获取

:::

```typescript
// 检查权限
  async checkPermission() {
    try {
      const manager = abilityAccessCtrl.createAtManager() // 创建程序控制管理器
      // 获取应用信息
      const buildInfo = bundleManager.getBundleInfoForSelfSync(bundleManager.BundleFlag.GET_BUNDLE_INFO_WITH_APPLICATION)
      const status = manager.checkAccessTokenSync(buildInfo.appInfo?.accessTokenId, "ohos.permission.MICROPHONE")
      if (status === abilityAccessCtrl.GrantStatus.PERMISSION_DENIED) {
        // 不被允许
        const context = getContext() as common.UIAbilityContext
        context.startAbility({
          bundleName: 'com.huawei.hmos.settings',
          abilityName: 'com.huawei.hmos.settings.MainAbility',
          uri: "application_info_entry",
          parameters: {
            pushParams: buildInfo.name
          }
        })
      } else {
        this.showVoiceCom = true
        this.beginCollectVoice()
      }
    } catch (error) {

    }
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711706833342-55e6a9e4-67df-4bc3-9cc5-c896ab736576.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_42%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708099277159-a1441e34-f299-4c41-9a64-07a23f45495a.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_14%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 新建utils/file_operate.ets(文件操作)

:::color2
因为后续视频和音频照片会频繁创建文件，所以封装一个公共的操作类

:::

```typescript
import { fileIo } from '@kit.CoreFileKit'

export class FileCommon {
  // 创建一个音频文件 并返回路径
  static createAudioFile() {
    let filePath = getContext().filesDir + '/' + Date.now() + '.wav'
    const file = fileIo.openSync(filePath, fileIo.OpenMode.CREATE)
    fileIo.closeSync(file)
    return filePath // 创建文件
  }
  static delFilePath (filePath: string) {
    if(filePath) {
      fileIo.unlinkSync(filePath)
    }
  }
}
```

+ 新建<font style="color:rgba(0, 0, 0, 0.9);">utils/audio_recorder.ets文件</font>

```typescript
import { audio } from '@kit.AudioKit'
import { fileIo } from '@kit.CoreFileKit'

export default class AudioCapturer {
  static audioCapturer: audio.AudioCapturer
  static audioStreamInfo: audio.AudioStreamInfo = {
    samplingRate: audio.AudioSamplingRate.SAMPLE_RATE_44100,
    channels: audio.AudioChannel.CHANNEL_1,
    sampleFormat: audio.AudioSampleFormat.SAMPLE_FORMAT_S16LE,
    encodingType: audio.AudioEncodingType.ENCODING_TYPE_RAW
  }
  static audioCapturerInfo: audio.AudioCapturerInfo = {
    source: audio.SourceType.SOURCE_TYPE_MIC, // 音源类型
    capturerFlags: 0 // 音频采集器标志
  }
  static recordIng: boolean = false

  // 是否正在录制

  // 是否正在录制
  // 初始化录音采集器
  static async init() {
    AudioCapturer.audioCapturer = await audio.createAudioCapturer({
      streamInfo: AudioCapturer.audioStreamInfo,
      capturerInfo: AudioCapturer.audioCapturerInfo
    });
  }

  static async start(filePath: string) {
    try {
      if (!AudioCapturer.audioCapturer) return
      AudioCapturer.recordIng = true
      await AudioCapturer.audioCapturer.start() // 开始录音
      let file = fileIo.openSync(filePath, fileIo.OpenMode.READ_WRITE | fileIo.OpenMode.CREATE); // 如果文件不存在则创建文件
      let fd = file.fd;
      let statFile = fileIo.statSync(fd)
      let bufferSize: number = statFile.size
      while (AudioCapturer.recordIng) {
        let size = await AudioCapturer.audioCapturer.getBufferSize();
        let buffer = await AudioCapturer.audioCapturer.read(size, true);
        if(buffer) {
            let options: FileOptions = {
                  offset: bufferSize,
                  length: buffer.byteLength
          };
            fileIo.writeSync(fd, buffer, options) // 写入文件
          bufferSize += buffer.byteLength
        }
  
      }
    } catch (error) {
      AlertDialog.show({
        message: JSON.stringify(error)
      })
    }

  }

  static async stop() {
    if (AudioCapturer.audioCapturer) {
      // 只有采集器状态为STATE_RUNNING或STATE_PAUSED的时候才可以停止
      if (AudioCapturer.audioCapturer.state === audio.AudioState.STATE_RUNNING ||
        AudioCapturer.audioCapturer.state === audio.AudioState.STATE_PAUSED
      ) {
        AudioCapturer.recordIng = false
        await AudioCapturer.audioCapturer.stop(); // 停止采集
      }

    }
  }

  // 释放资源
  static async release() {
    if (AudioCapturer.audioCapturer) {
      await AudioCapturer.audioCapturer.release()
    }
  }
}

export class FileOptions {
  offset: number = 0;
  length: number = 0
}
```

:::color1
+ 在BottomInput中使用

:::

+ 初始化时进行init，卸载组件时进行release

```typescript
aboutToAppear(): void {
    AudioCapturer.init()
  }
  aboutToDisappear(): void {
    AudioCapturer.release()
  }
```

 

:::color2
当长按时，创建文件开始录音

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711809638399-66482dfd-09f0-4c82-91e7-e082c60d3ad0.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_37%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 声明一个变量记录临时音频存储的路径地址

```typescript
tempAudioPath: string = "" // 临时录音变量
```

+ 收集录音的方法

```typescript
 // 开始收集声音
  beginCollectVoice() {
    this.tempAudioPath = FileCommon.createAudioFile()
    AudioCapturer.start(this.tempAudioPath) // 开始录音
  }
```

+ 关闭录音的方法

```typescript
  // 停止语音收集
  stopCollectVoice () {
    AudioCapturer.stop()
  }
```

:::color2
在移动到左侧时松手时，将原有文件删除

:::

```typescript
// 松手判断逻辑
  releaseFinger () {
    this.showVoiceCom = false
    this.stopCollectVoice() // 先关闭录音
    if(this.voiceState === VoiceRecordEnum.Cancel) {
      // 如果松手时，是取消状态 不管录的语音怎么样 直接删除
      FileCommon.delFilePath(this.tempAudioPath) // 删除路径
    }else if(this.voiceState === VoiceRecordEnum.Transfer) {
      // 如果是转化文本类
    }
    else if(this.voiceState === VoiceRecordEnum.RecordIng) {
      // 如果是正常录音 发送语音信息
    }
    this.voiceState = VoiceRecordEnum.RecordIng
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711814541220-1e47a24a-27a3-4ad3-9bb2-74339c14c353.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_36%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::

<h1 id="lTpgA">计算音频时长</h1>
:::color1
+ 只要开始录音-就计时，暂停，就不再计时，结束停止计时

:::

+ 定义时间变量

```typescript
 // 计算计时器
  duration: number = 0 // 秒
 
  timer: number = -1 // 定时器标记

```

+ 定义开始和结束两个方法

```typescript
 // 开始计时
  startTime () {
    this.timer = setInterval(() => {
      this.duration++
    }, 1000)
  }
  // 结束计时
  endTime () {
    clearInterval(this.timer)
  }
```

+ 开始计时和结束计时

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711815373403-8755b3e0-9984-400e-a7a2-de090ccb437f.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_51%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708018458952-0629b658-c47c-46b1-90ff-3f72408cc864.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::

<h1 id="C4yrN">创建语音消息发送</h1>
:::color1
当松手时，状态为录制发送时，将语音消息发送一条信息

:::

+ 在BottomInput中导入当前用户和对话用户

```typescript
  @StorageProp(WeChat_CurrentUserKey)
  currentUser: UserInfoModel = new UserInfoModel({} as UserInfo)
  @Consume
  talkUser: UserInfoModel
```

+ 在BottomInput中声明一个方法

```typescript
  sendAudioMessage: (mess: MessageInfoModel) => void = () => {}
```

+ 新建一个发送语音信息的方法

```typescript
 // 发送语音消息
  sendAudio () {
    let mess = new MessageInfoModel({
      sourceDuration: this.duration,
      messageContent: `[语音]${this.duration}"`,
      connectUser: this.talkUser,
      sendUser: this.currentUser,
      messageType: MessageTypeEnum.AUDIO,
      sourceFilePath: this.tempAudioPath
    } as MessageInfo)
    this.sendAudioMessage(mess)
    this.tempAudioPath = "" // 清空临时路径
    this.duration = 0 // 时长归零
  }
```

+ 松手时，发送语音信息

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711816082370-5f1d5187-3aa3-4e94-af16-f08b9540d851.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_44%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 在父组件传入发送语音的方法

```typescript
// 发送语音消息
  async sendAudioMessage (mess: MessageInfoModel) {
    this.messList.push(mess) // 添加到信息的底部
    this.scroller.scrollEdge(Edge.Bottom) // 滚动到最底部
    WeChatStore.addOneWeChatMessage(this.talkUser.user_id, mess) // 添加到聊天记录
  }
```

+ 传递方法

```typescript
   //  放置底部组件
      BottomInput({
        sendTextMessage: (content: string) => {
          this.sendTextMessage(content)
        },
        sendAudioMessage: (mess: MessageInfoModel) => {
          this.sendAudioMessage(mess)
        }
      })
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708019433851-c9c517db-435a-47b7-80dc-89e7ae46fbde.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::

<h1 id="YrTS1">渲染语音场景下的消息组件</h1>
+ 加上一个判断，当录制时长小于1秒时，处理语音销毁

```typescript
  else if (this.voiceState === VoiceRecordEnum.RecordIng) {
      // 如果是正常录音 发送语音信息
      if(this.duration < 1) {
        promptAction.showToast({ message: '录制声音时间太短' })
        FileCommon.delFilePath(this.tempAudioPath) // 删除路径
        return
      }
      this.sendAudio()
    }
```

:::color1
当发送的消息为语音时，渲染语音条

:::

+ 实现多个方法

```typescript
  // 获取文本消息
  @Builder
  getTextContent() {
    Text(this.currentMessage.messageContent)
      .backgroundColor(this.isOwnMessage ? $r('app.color.second_primary') : $r('app.color.white'))
      .fontColor($r('app.color.text_primary'))
      .padding(10)
      .lineHeight(24)
      .margin({
        left: 10,
        right: 10
      })
      .borderRadius(5)
  }
  // 获取语音宽度
  getAudioWidth () {
    let minWidth: number = 20
    let maxWidth: number = 90
    let calWidth: number = minWidth + (100 * this.currentMessage.sourceDuration / 60)
    if(calWidth > maxWidth) return maxWidth+"%"
    return calWidth+"%"
  }
  // 获取语音显示
  @Builder
  getAudioContent () {
    Row({ space: 5 }) {
      Text(`${this.currentMessage.sourceDuration}'`)
        .textAlign(TextAlign.Center)
      Image($r("app.media.ic_public_recorder"))
        .width(20)
        .height(20)
        .rotate({
          angle: this.isOwnMessage ? 180 : 0
        })
    }
    .width(this.getAudioWidth())
    .backgroundColor(this.isOwnMessage ? $r('app.color.chat_primary') : $r('app.color.white'))
    .justifyContent(this.isOwnMessage ? FlexAlign.End : FlexAlign.Start)
    .height(40)
    .padding({
      left: 10,
      right: 10
    })
    .margin({
      left: 10,
      right: 10
    })
    .borderRadius(4)
    .direction(this.isOwnMessage ? Direction.Ltr :  Direction.Rtl )
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711888178739-e3cf7a49-d000-4829-aa16-ed77dc48531e.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_54%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708019917168-d28e1070-f9b3-4d2f-8552-3fc28fd09369.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::



<h1 id="NgYBa">播放语音AudioRender</h1>
+ 创建一个audio_renderer的静态类

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711888316834-61c103db-ef74-4806-a962-48119acff47b.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_38%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ utils/audio_renderer

```typescript
// 用来播放pcm音频
import { audio } from '@kit.AudioKit'
import { fileIo } from '@kit.CoreFileKit';

export class AudioRenderer {
  static renderIng: boolean = false // 是否正在播放
  // 实例
  static renderModel: audio.AudioRenderer
  // 采样配置
  static audioStreamInfo: audio.AudioStreamInfo = {
    samplingRate: audio.AudioSamplingRate.SAMPLE_RATE_16000,
    channels: audio.AudioChannel.CHANNEL_1,
    sampleFormat: audio.AudioSampleFormat.SAMPLE_FORMAT_S16LE,
    encodingType: audio.AudioEncodingType.ENCODING_TYPE_RAW
  };
  static audioRendererInfo: audio.AudioRendererInfo = {
    rendererFlags: 0, // 音频渲染器 0 普通  1 低时延 (不支持)
    usage: audio.StreamUsage.STREAM_USAGE_MOVIE
    // 场景
  }
  // 创建播放器的参数准备好了
  static audioRendererOptions: audio.AudioRendererOptions = {
    streamInfo: AudioRenderer.audioStreamInfo,
    rendererInfo: AudioRenderer.audioRendererInfo
  }
  // 初始化方法
  static async init () {
      if(!AudioRenderer.renderModel) {
        // 创建实例
        AudioRenderer.renderModel = await audio.createAudioRenderer(AudioRenderer.audioRendererOptions)
      }
  }
  // 音频的释放和暂停
  static async stop () {
    if(AudioRenderer.renderModel && AudioRenderer.renderModel.state === audio.AudioState.STATE_RUNNING) {
      AudioRenderer.renderIng = false
     await AudioRenderer.renderModel.stop() // 通知方法

    }
  }
  // 开始语音播放
  static  async start (filePath: string, callback?: () => void) {
    if(AudioRenderer.renderModel && filePath) {
      // 先管一下状态
      // 如果你在播的情况下 还能播吗？
      // 什么情况下能播？ 暂停 停止 准备
      let stateList:  audio.AudioState [] = [
        audio.AudioState.STATE_PREPARED,
        audio.AudioState.STATE_PAUSED,
        audio.AudioState.STATE_STOPPED
      ]
      if(!stateList.includes(AudioRenderer.renderModel.state)) {
        // 不包含的情况下 此时就不能播了
        return
      }
      // 此时可以播
      AudioRenderer.renderIng = true

      await AudioRenderer.renderModel.start() // 启动播放
      // 读写文件 filePath的文件 一段段的读取 读完拉到 关闭文件 停止播放
     const file = fileIo.openSync(filePath, fileIo.OpenMode.READ_ONLY) // 读这个文件的buffer  一段段的读取 1280
      const stat = fileIo.statSync(file.fd) // 详细信息
      const bufferSize = await AudioRenderer.renderModel.getBufferSize() // 获取缓冲区的长度
      let buf = new ArrayBuffer(bufferSize) // 创建一个缓冲区对象 长度是音频采集器长度的长度
      let totalSize = 0 // 总量值
      while (totalSize < stat.size &&  AudioRenderer.renderIng) {
         fileIo.readSync(file.fd, buf, {
           offset: totalSize,
           length: bufferSize
         })
        // 坑点- write是个异步方法  需要一段段的去播放 需要写入完这一段以后 再去写入下一段
         await AudioRenderer.renderModel.write(buf) // 往音频采集器写入缓冲区内容  播完再下一段
        if (AudioRenderer.renderModel!.state.valueOf() === audio.AudioState.STATE_RELEASED) { // 如果渲染器状态为released，关闭资源
          fileIo.close(file);
        }
        // 此时要继续
        totalSize += bufferSize
      }
      // 关闭文件
      fileIo.closeSync(file.fd)
      AudioRenderer.stop() // 关闭
      callback && callback()
    }
  }
  // 释放
  static async release () {
    if(AudioRenderer.renderModel) {
      await AudioRenderer.renderModel.release() // 释放方法
    }
  }
}
```

+ 在详情中初始化(ChatDetail)

```typescript
aboutToAppear(): void {
    AudioRenderer.init()
  }
  aboutToDisappear(): void {
    AudioRenderer.stop()
  }
```

+ 点击声音播放

```typescript
.onClick(() => {
      AudioRenderer.start(this.currentMessage.sourceFilePath)
    })
```

:::color2
播放声音图片帧[声音帧动画.zip](https://weiqi123.yuque.com/attachments/yuque/0/2024/zip/32778948/1727514411336-e2029eba-73f8-4276-bf36-2bdc922a82a7.zip)

:::

+ 放入到资源目录下

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712044768453-41e8d48a-f58c-4815-8adf-73a4db140975.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 替换声音消息的位置，使用图片帧组件

```typescript
ImageAnimator()
        .images([
           {
            src: $r("app.media.ic_public_voice3")
          },
          {
            src: $r("app.media.ic_public_voice1")
          },
          {
            src: $r("app.media.ic_public_voice2")
          },
          {
            src: $r("app.media.ic_public_voice3")
          }
        ])
        .iterations(-1)
        .state(this.audioState)
        .width(20)
        .height(20)
        .rotate({
          angle: this.isOwnMessage ? 180 : 0
        })
```

+ 声明状态audioState

```typescript
 @State
  audioState: AnimationStatus = AnimationStatus.Initial
```

+ 播放时设置状态

```typescript
 .onClick(() => {
      AudioRenderer.start(this.currentMessage.sourceFilePath)
      this.audioState = AnimationStatus.Running
    })
```

+ 在AudioRenderer中实现传入一个回调函数，播放结束时，执行

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712046162491-e20a8dad-af3a-459e-b836-5008975ac172.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_59%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712046172338-82cf0175-ddf9-40a7-bcdd-8737d888b984.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_61%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 播放传入回调，结束图片帧动画

```typescript
 .onClick(async () => {
        await AudioRenderer.stop() // 点击先停止播放
        this.audioState = AnimationStatus.Initial
        AudioRenderer.start(this.currentMessage.sourceFilePath, () => {
          this.audioState = AnimationStatus.Stopped
        }) // 播放
        this.audioState = AnimationStatus.Running
      })
```

:::color3
提交代码

:::





<h1 id="J2pOG">删除消息时，删除临时语音文件</h1>
:::color2
在删除单条消息时，如果存在临时引用路径则直接删除

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711941984519-3d06e7a9-b382-46c4-a442-c1d2c1d270c8.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_51%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
删除整个聊天记录时，得遍历查找

需要在首选项中的删除语音的方法实现

:::

```typescript
 // 删除“我”和某个人的整个的聊天记录
  static async delWeChatMessage(userId: string) {
    // 检查是否有引用文件 如果有全删除掉
   const list = WeChatStore.getWeChatMessage(userId)
    list.forEach(item => {
      if(item.sourceFilePath) {
        FileCommon.delFilePath(item.sourceFilePath) // 删除我和你之间所有的引用文件
      }
    })
    preferences.deletePreferences(getContext(), {
      name: `${WeChat_UserRecordKey}_${userId}`
    })
  }
```

<h1 id="YtBpk">发送信息-增加声音提示</h1>
:::color3
给$rawfile目录下放置以下声音的素材

[声音.zip](https://weiqi123.yuque.com/attachments/yuque/0/2024/zip/32778948/1727514411344-bbc00c77-297f-4037-ab1e-2bc7aa6bb5a9.zip)

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708101636078-a40e16b9-2cd6-4b6d-a27b-8289889e6a13.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_26%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 封装AvPlayer播放类

:::color2
avplayer特点是 1个实例播出一种声音，多实例声音允许重叠

:::

:::color2
因为AvPlayer可以实现多实例播放，所以这里我们采用实例方式进行播放

:::



![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1711951136560-43c2bba2-859c-4d7b-a200-e6a0beb4c96b.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_42%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 新建utils/av_player.ets

```typescript
import media from '@ohos.multimedia.media'

export class AvPlayer {
  avPlayer: media.AVPlayer | null = null
  async init() {
    this.avPlayer = await media.createAVPlayer()
    this.watchCallBack()
  }
  watchCallBack () {
    this.avPlayer?.on("stateChange", (state: string) => {
      switch (state) {
        case 'initialized': // avplayer 设置播放源后触发该状态上报
          console.info('AVPlayer state initialized called.');
          this.avPlayer?.prepare()
          break;
        case 'prepared': // prepare调用成功后上报该状态机cesi
          console.info('AVPlayer state prepared called.');
          this.avPlayer?.play()
          break;
        case 'playing': // play成功调用后触发该状态机上报
          console.info('AVPlayer state playing called.');
          break;
        case 'paused': // pause成功调用后触发该状态机上报
          console.info('AVPlayer state paused called.');
          break;
        case 'completed': // 播放结束后触发该状态机上报
          console.info('AVPlayer state completed called.');
          this.avPlayer?.reset(); //调用播放结束接口
          break;
        case 'stopped': // stop接口成功调用后触发该状态机上报
          console.info('AVPlayer state stopped called.');
          this.avPlayer?.reset(); //调用播放结束接口
          break;
        case 'released':
          console.info('AVPlayer state released called.');
          this.avPlayer?.reset(); //调用播放结束接口
          break;
        case 'error':
          console.error('AVPlayer state error called.')
          this.avPlayer?.reset(); //调用播放结束接口
          break;
        default:
          console.info('AVPlayer state unknown called.');
          break;
      }
    })
  }
  async play(fileName: string) {
    let fileDescriptor = await getContext().resourceManager.getRawFd(fileName);
    let avFileDescriptor: media.AVFileDescriptor =
      { fd: fileDescriptor.fd, offset: fileDescriptor.offset, length: fileDescriptor.length }
    this.avPlayer!.fdSrc = avFileDescriptor
  }
  async stop () {
    await this.avPlayer?.stop()
  }
  async release () {
    await this.avPlayer?.release()
  }
}
```

+ 在ChatDetail中初始化时进行初始化

```typescript
 player: AvPlayer = new AvPlayer() // 初始化avplayer
  aboutToAppear(): void {
    this.player.init()
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712030353615-4769fbf8-9c4d-4674-93bc-f18147273c0c.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_40%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 发送消息时播放音乐

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712030427988-effbfc50-c6d2-4a9b-8aad-7efef01e225e.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_52%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 发送语音时播放音乐

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712032581258-caab77d9-b99f-4d9a-b8a2-02c8bb9cb04b.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_61%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color3
提交代码

:::



<h1 id="lY77F">渲染底部输入菜单</h1>
![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708101809193-4d51294e-c346-48ff-ba40-b23ea7fdae7b.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color3
继续使用之前定义的models/popup.ets中的PopupItem类型

在BottomInput中声明底部的八个数据

:::

```typescript
@State
  bottomList: PopupItem[] = [{
    icon: $r('app.media.ic_public_photo'),
    title: '照片',
  }, {
    icon: $r('app.media.ic_public_carema'),
    title: '拍摄',

  }, {
    icon: $r('app.media.ic_statusbar_gps'),
    title: '位置',

  }, {
    icon: $r('app.media.ic_public_voice'),
    title: '语音输入',

  }, {
    icon: $r("app.media.ic_public_collect"),
    title: '收藏',

  }, {
    icon: $r("app.media.ic_public_contacts_filled"),
    title: '个人名片',

  }, {
    icon: $r("app.media.ic_public_folder_filled"),
    title: '文件',

  }, {
    icon:  $r("app.media.ic_public_music_filled"),
    title: '音乐',
  }]

  @State
  showBottomCard: boolean = false // 显示底部

```

+ 在底部渲染

```typescript
 if (this.showBottomCard) {
        // 底部结构
        GridRow({ columns: 4 }) {
          ForEach(this.bottomList, (item: PopupItem) => {
            GridCol() {
              this.getBottomCard(item)
            }.height(100)
          })
        }
        .width('100%')
      
      }

```

+ 声明一个自定义渲染builder

```typescript
@Builder
  getBottomCard(item: PopupItem) {
    Column() {
      Column() {
        Image(item.icon)
          .width(30)
          .height(30)
          .fillColor("#4c4c4c")
      }
      .backgroundColor(Color.White)
      .width(56)
      .aspectRatio(1)
      .borderRadius(10)
      .justifyContent(FlexAlign.Center)
      .alignItems(HorizontalAlign.Center)

      Text(item.title)
        .fontSize(12)
        .fontColor($r('app.color.text_second'))
        .margin({
          top: 10
        })
    }.layoutWeight(1)
    .alignItems(HorizontalAlign.Center)
    .onClick(() => {
      item.itemClick && item.itemClick()
    })
  }
```



+ 点击右侧加号进行折叠展开

 ![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712033769569-e1ea885e-8eaa-45c4-9b6e-b98d710213ec.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_46%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 键盘聚焦关闭底部
+ 声明一个TextController

```typescript
  textController: TextInputController = new TextInputController()

```

+ 绑定TextInput组件-点击时隐藏底部卡片

```typescript
 TextInput({ text: $$this.content, controller: this.textController })
.onClick(() => {
              animateTo({ duration: 100 }, () => {
                this.showBottomCard = false
              })
            })
```

+ 切换语音文本时，关掉下方的弹层

```typescript
 Image(this.showVoice ? $r('app.media.ic_public_keyboard') : $r('app.media.ic_public_sound'))
          .width(25)
          .height(25)
          .onClick(() => {
            this.showVoice = !this.showVoice
            if(this.showVoice) {
              animateTo({ duration: 100 }, () => {
                this.showBottomCard = false
              })
            }
          })
```



![](https://cdn.nlark.com/yuque/0/2024/gif/8435673/1708103781071-3b8a3573-cd0f-49fa-bda3-67d9f31c0bc2.gif)



:::color3
提交代码

:::

<h1 id="GH5fT"></h1>
:::color2
悲观者正确 乐观者前行

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712833989766-c28b5b8e-441f-4664-85c0-a19f2afb2080.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_23%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
当松手时，取消状态直接设置时长为0

:::

+ 推送 PushKit . - 不需要鸿蒙端写代码

:::color2
需要服务端支持

讲思路帮大家去面试

:::

:::color2
Kit能力太多了 - 50000个API

:::

<h1 id="Z4btn">选择图片-发送照片</h1>
:::color2
打开相册- 不需要权限-获取照片或者视频

等同于前端的 input type='file'

:::



:::color2
致命问题： 目前模拟器不允许拖照片进去

怎么办？

:::

:::color2
相册不允许随意的写入

1. 安全组件 SaveButton 组件 给5秒钟的时间获取写入权限 5秒收回
2. 发邮件 将自己的包名和申请相册理由写入

:::

:::color2
[https://gitee.com/shuiruohanyu/copy_image](https://gitee.com/shuiruohanyu/copy_image)

:::



:::color3
+ 点击图片时，选择多张图片，进行发送

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708104098527-aaf22cce-fc58-47d3-8258-d5178441485e.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_38%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 在BottomInput中定义sendPhoto方法

```typescript
 // 发送照片方法
  async sendPhoto() {
    const photo = new picker.PhotoViewPicker()
    const result = await photo.select({
      maxSelectNumber: 9,
      MIMEType: picker.PhotoViewMIMETypes.IMAGE_TYPE
    })
    if (result.photoUris.length) {
      let imgList: MessageInfoModel[] = []
      result.photoUris.forEach(item => {
        // 拷贝文件到沙箱
        const file = fileIo.openSync(item, fileIo.OpenMode.READ_ONLY)
        let newFileName = getContext().filesDir + '/' + Date.now() + '.jpg'
        fileIo.copyFileSync(file.fd, newFileName)
        const newMess = new MessageInfoModel({
          connectUser: this.talkUser,
          sendUser: this.currentUser,
          messageContent: '[图片]',
          messageType: MessageTypeEnum.IMAGE,
          sourceFilePath: newFileName
        } as MessageInfo)
        imgList.push(newMess) // 添加到列表
        fileIo.closeSync(file.fd) // 释放资源
      })
      this.sendImageList(imgList)
       // 关闭底部
    animateTo({ duration: 150 }, () => {
      this.showBottomCard = false
    })
    }
  }
```

+ 子组件接入一个方法

```typescript
  // 发送图片消息
  sendImageList: (list: MessageInfoModel[]) => void = () => {}
```

+ 父组件定义方法

```typescript
// 发送图片消息
  async sendImgMessage (list: MessageInfoModel[]) {
    this.messList.push(...list)
    this.scroller.scrollEdge(Edge.Bottom) // 滚动到最底部
    list.forEach(item => {
      WeChatStore.addOneWeChatMessage(this.talkUser.user_id, item) // 添加到聊天记录
    })
    this.player.play("send.wav")
  }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712046755786-23ccaaf4-6db9-495c-b1be-5fac6552bc48.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_42%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 渲染图片信息

```typescript
 // 获取图片显示
  @Builder
  getImageContent() {
    Column() {
      Image("file://" + this.currentMessage.sourceFilePath)
        .borderRadius(4)
        .width('100%')
        .enabled(false)
    }
    .width('40%')
    .margin({
      left: 10,
      right: 10
    })

  }
```

+ 根据不同条件渲染

```typescript
if(this.currentMessage.messageType === MessageTypeEnum.TEXT) {
            // 文本消息
            this.getTextContent()
          }
          if(this.currentMessage.messageType === MessageTypeEnum.AUDIO) {
            // 语音消息
            this.getAudioContent()
          }
          if(this.currentMessage.messageType === MessageTypeEnum.IMAGE) {
            // 语音消息
            this.getImageContent()
          }
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708160290352-0a43fb9b-74f3-4962-810e-6662aaf46dc4.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_31%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color3
提交代码

:::



<h1 id="pqJFu">图片预览</h1>
:::color2
图片需要长按删除

:::

:::color1
当点击图片时，弹出层进行渲染

:::

+ 新建一个ChatDetail/Components/PreviewImg.ets文件

```typescript
@CustomDialog
struct PreviewImage {
  controller: CustomDialogController
  url: string = ""
  build() {
    Column() {
      Image(this.url)
        .width('100%')
    }
    .width('100%')
    .height('100%')
    .backgroundColor(Color.Black)
    .onClick(() => {
      this.controller.close()
    })
    .justifyContent(FlexAlign.Center)
  }
}
export default PreviewImage
```

+ 在ChatDetail中进行定义

```typescript
 previewUrl: string = ""
  previewController: CustomDialogController = new CustomDialogController({
    builder: PreviewImg({
      url: this.previewUrl
    }),
    autoCancel: false,
    customStyle: true
  })
```

+ Message组件声明一个函数变量

```typescript
  previewImage: () => void = () => {}
```

+ 点击图片调用

```typescript
// 获取图片显示
  @Builder
  getImageContent() {
    Column() {
      Image("file://" + this.currentMessage.sourceFilePath)
        .borderRadius(4)
        .width('100%')
        .enabled(false)
    }
    .width('40%')
    .margin({
      left: 10,
      right: 10
    }).onClick(() => {
      this.previewImage()
    })

  }
```

+ 父组件传入方法ChatDetail

```typescript
  Message({
              currentMessage: item, delMessage: (messId: string) => {
                this.delMessage(messId)
              },
              previewImage: () => {
               this.previewUrl = "file://" + item.sourceFilePath
                this.previewController.open()
              }
            })
```

:::color1
提交代码

:::



<h1 id="wal8B">唤起相机拍照发送照片</h1>
:::color2
两种方式

+ 极其复杂的需要各种各样的对象 
+ 最简单的方式 。picker 

:::

+ BottomInput.ets 注册唤起相机

```typescript
{
    icon: $r('app.media.ic_public_carema'),
    title: '拍摄',
    itemClick: () => {
      this.openCamera()
    }

  }
```

+ 实现打开相机方法

```typescript
 // 打开相机
  async openCamera() {
    try {
      let pickerProfile: cameraPicker.PickerProfile = {
        cameraPosition: camera.CameraPosition.CAMERA_POSITION_BACK
      };
      let pickerResult: cameraPicker.PickerResult = await cameraPicker.pick(getContext(),
        [cameraPicker.PickerMediaType.PHOTO, cameraPicker.PickerMediaType.VIDEO], pickerProfile);
      console.log("the pick pickerResult is:" + JSON.stringify(pickerResult));
    } catch (error) {
      promptAction.showToast({
        message: '相机打开异常'
      })
    }
  }
```

+ 拍摄照片

```typescript
 if (pickerResult.mediaType === "photo") {
        // 奇葩bug 直接判断枚举得到的是false
        // 如果是图片
        const imgPath = getContext().filesDir + '/' + Date.now() + '.jpg'
        const file = fileIo.openSync(pickerResult.resultUri, fileIo.OpenMode.READ_ONLY)
        fileIo.copyFileSync(file.fd, imgPath) // 拷贝文件
        const newMess = new MessageInfoModel({
          connectUser: this.talkUser,
          sendUser: this.currentUser,
          messageContent: '[图片]',
          messageType: MessageTypeEnum.IMAGE,
          sourceFilePath: imgPath
        } as MessageInfo)
        this.sendImageList([newMess])
      }
```



:::color1
提交代码

:::

<h1 id="k2vEx">发送视频</h1>
+ 根据类型不同处理不同的图片和视频

```typescript
  // 打开相机
  async openCamera() {
    try {
      let pickerProfile: cameraPicker.PickerProfile = {
        cameraPosition: camera.CameraPosition.CAMERA_POSITION_BACK
      };
      let pickerResult: cameraPicker.PickerResult = await cameraPicker.pick(getContext(),
        [cameraPicker.PickerMediaType.PHOTO, cameraPicker.PickerMediaType.VIDEO], pickerProfile);

      let imgPath = getContext().filesDir + '/' + Date.now() + '.'
      let extendName = "jpg"
      let messType = MessageTypeEnum.IMAGE
      let messContent = '[图片]'
      if (pickerResult.mediaType === "video") {
        // 奇葩bug 直接判断枚举得到的是false
        // 如果是视频
        extendName = "mp4"
        messType = MessageTypeEnum.VIDEO
        messContent = "[视频]"
      }
      const file = fileIo.openSync(pickerResult.resultUri, fileIo.OpenMode.READ_ONLY)
      fileIo.copyFileSync(file.fd, imgPath + extendName) // 拷贝文件
      const newMess = new MessageInfoModel({
        connectUser: this.talkUser,
        sendUser: this.currentUser,
        messageContent: messContent,
        messageType: messType,
        sourceFilePath: imgPath + extendName
      } as MessageInfo)
      this.sendImageList([newMess])
    } catch (error) {
      promptAction.showToast({
        message: '相机打开异常'
      })
    }
  }
```

:::color1
在Message.ets中添加视频消息判断

:::

```typescript
  if (this.currentMessage.messageType === MessageTypeEnum.VIDEO) {
            // 语音消息
            this.getVideoContent()
          }
```

+ 定义VideoController

```typescript
  videoController: VideoController = new VideoController() // 视频controller

```

+ 渲染一个视频模式下的builder

```typescript
 @Builder
  getVideoContent() {
    Column() {
      Stack() {
        Video({
          src: "file://" + this.currentMessage.sourceFilePath,
          controller: this.videoController
        })
          .controls(false)
          .width(100)
          .height(150)
          .borderRadius(4)
          .id(this.currentMessage.id)
          .onPrepared(async () => {
            this.videoController.setCurrentTime(0.1) // 拨到0.1秒
          })
        Image($r("app.media.ic_public_play"))
          .width(30)
          .height(30)
          .fillColor($r("app.color.back_color"))
      }
    }
    .margin({
      left: 10,
      right: 10
    })
  }
```

+ 点击视频渲染

```typescript
 .onClick(() => {
      this.previewImage()
    })
```

+ 预览组件支持图片和视频预览

```typescript
import { MessageTypeEnum } from '../../../models/message'

@CustomDialog
struct PreviewImage {
  controller: CustomDialogController
  url: string = ""
  showType: MessageTypeEnum = MessageTypeEnum.IMAGE
  build() {
    Column() {
      if(this.showType === MessageTypeEnum.IMAGE) {
        Image(this.url)
          .width('100%')
      }
      if(this.showType === MessageTypeEnum.VIDEO) {
        Video({
          src: this.url
        })
          .loop(true)
          .autoPlay(true)
          .controls(false)
          .width('100%')
          .height('100%')
      }

    }
    .width('100%')
    .height('100%')
    .backgroundColor(Color.Black)
    .onClick(() => {
      this.controller.close()
    })
    .justifyContent(FlexAlign.Center)
  }
}
export default PreviewImage
```

+ 在ChatDetail中传入对应的参数

```typescript
showType: MessageTypeEnum = MessageTypeEnum.IMAGE
previewController: CustomDialogController = new CustomDialogController({
    builder: PreviewImg({
      url: this.previewUrl,
      showType: this.showType
    }),
    autoCancel: false,
    customStyle: true
  })
```

+ 在传递给Message组件时，传入type

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712218598647-287a01e7-0042-4169-b2d7-b3906b8fae38.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_49%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::

<h1 id="eC8dt">发送位置组件</h1>
:::color2
参考链接：[官方文档](https://developer.huawei.com/consumer/cn/doc/app/agc-help-harmonyos-releaseapp-0000001126380068)

:::

:::color2
华为地图必须调试证书才能显示

:::

:::color2
<h2 id="RxCx2"><font style="color:rgba(0, 0, 0, 0.9);">生成签名证书指纹</font></h2>
需要进行一系列的配置操作

+ p12文件
+ csr文件
+ cer文件-调试证书
+ p7b文件-调试证书

AGC开启地图服务

配置应用包和证书

配置项目的module.json5中的应用指纹

:::

:::color2
**<font style="color:#DF2A3F;">注意：目前只能采用调试证书查看地图，发布证书目前模拟器无法渲染地图</font>**

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712990537451-65cdb13a-a843-465f-a783-c96fa8e02e62.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_30%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 配置client_id

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712988775048-57be56a4-fce0-4153-bfad-6605165bd82c.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_28%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 添加证书指纹

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712988814713-dbc236b1-91ba-407c-81d5-72fea624e38e.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_28%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 添加调试设备见图

:::color2
添加Profile时 选择所有的设备

:::

地图展示

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712990650458-7db7bdb8-eef3-45b8-aba8-4801e402b710.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_30%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

```typescript
import { MapComponent, mapCommon, map } from '@kit.MapKit';
import { AsyncCallback } from '@kit.BasicServicesKit';
```



+ 新建地图组件-ChatDetail/Components/Locaiton.ets

```typescript
import { MapComponent } from '@hms.core.map.MapComponent';

@Component
struct Location {

  build() {
    Row() {
      MapComponent({
        mapOptions: {
          position: {
            target: {
              latitude: 39.9,
              longitude: 116.4
            },
            zoom: 10
          }
        },
        mapCallback: () => {}
      }).width('100%').height('100%')
    }
    .height('100%')
  }
}

export default Location
```

+ 定义变量

```typescript
  @State
  showLocation: boolean = false

```

+ 定义位置的builder

```typescript
 @Builder
  getLocation() {
    Stack({ alignContent: Alignment.Top }) {
      Location()
      Row () {
        Text("取消")
          .fontColor($r("app.color.text_second"))
          .fontWeight(FontWeight.Bold)
        Button("发送")
          .type(ButtonType.Normal)
          .borderRadius(4)
          .backgroundColor($r("app.color.pay_back"))
          .fontColor($r("app.color.white"))
          .height(30)
          .width(60)
      }
      .justifyContent(FlexAlign.SpaceBetween)
      .padding({
        left: 20,
        right: 20
      })
      .width('100%')
      .height(60)
      .margin({
        top: 50
      })
    }
    .width('100%')
  }
```

+ 绑定弹层

:::color2
因为之前绑定了语音输出组件的弹层，所以这里的弹层要绑定在其他位置

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712331669446-9e4718c3-24ca-46b8-8999-6cb65ddc96b9.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_57%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712331620038-039eab31-1b64-4a80-ad3e-cfa892798d4f.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_10%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color1
提交代码

:::

<h1 id="dHn5H">获取当前位置</h1>
:::color2
模拟器打开开关

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712993158339-987687ca-139f-43f7-91d9-74c51dc189e7.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_12%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::

:::color2
+ 申请读取位置权限
+ 获取经纬度
+ 设置经纬度

:::

+ 设置经纬度位置权限module.json5

```typescript
 {
        "name": "ohos.permission.LOCATION",
        "reason": "$string:LOCATION_REASON",
        "usedScene": {
          "abilities": ["EntryAbility"],
          "when": "always"
        }
      },
      {
        "name": "ohos.permission.APPROXIMATELY_LOCATION",
        "reason": "$string:LOCATION_REASON",
        "usedScene": {
          "abilities": ["EntryAbility"],
          "when": "always"
        }
      },
```

+ 在ability中申请定位

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712332050243-2f89d690-c027-43d0-9193-db4a720ddac3.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_54%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 在Locaiton组件中声明一个回调函数获取MapController

```typescript
import { AsyncCallback } from '@kit.BasicServicesKit';
import { MapComponent, mapCommon, map } from '@kit.MapKit';


@Component
struct Location {
  callback?: AsyncCallback<map.MapComponentController>;
  mapController?: map.MapComponentController;
  aboutToAppear(): void {
    this.callback = async (err, mapController) => {
      if (!err) {
        // 获取地图的控制器类，用来操作地图
        this.mapController = mapController;
      }
    };
  }
  build() {
    Row() {
      MapComponent({
        mapOptions: {
          position: {
            target: {
              latitude: 39.9,
              longitude: 116.4
            },
            zoom: 10
          }
        },
        mapCallback: this.callback
      }).width('100%').height('100%')
    }
    .height('100%')
  }
}

export default Location
```

+ 获取位置后初始化设置我的位置

```typescript
 this.callback = async (err, mapController) => {
      if (!err) {
        // 获取地图的控制器类，用来操作地图
        this.mapController = mapController;
        this.mapController.setMyLocationEnabled(true)
        this.mapController.setMyLocationControlsEnabled(true)
        // 启用我的位置图层
         this.getLocation()
      }
    };
```

+ 获取位置方法

```typescript
import { MapComponent, mapCommon, map } from '@kit.MapKit';
import { AsyncCallback } from '@kit.BasicServicesKit';
import { geoLocationManager } from '@kit.LocationKit';

@Component
struct Location {
  // 初始化地图的属性
  private mapOption: mapCommon.MapOptions = {
    position: {
      target: {
        latitude: 39.9,
        longitude: 116.4
      },
      zoom: 12
    }
  };
  private callback?: AsyncCallback<map.MapComponentController>;
  private mapController?: map.MapComponentController;
  @Link
  currentAddress: string
  aboutToAppear(): void {
    // 地图初始化的回调
    this.callback = async (err, mapController) => {
      if (!err) {
        // 获取地图的控制器类，用来操作地图
        this.mapController = mapController;
        this.mapController.setMyLocationEnabled(true) // 允许我的定位
        this.mapController.setMyLocationControlsEnabled(true) // 允许我的定位组件显示
        // 此时此刻 可以拿定位了
        this.getLocation()
      }
    };
  }

  async getLocation() {
    try {
      const result = await geoLocationManager.getCurrentLocation()
      // result.latitude
      this.mapController?.setMyLocation({
        latitude: result.latitude,
        longitude: result.longitude,
        altitude: 0,
        accuracy: 0,
        speed: 0,
        timeStamp: 0,
        direction: 0,
        timeSinceBoot: 0
      })
      // 地图上你所看到的东西 实际上是照相机对象的镜头位置
      let cameraUpdate: map.CameraUpdate = map.newCameraPosition({
        target: {
          longitude: result.longitude,
          latitude: result.latitude
        },
        zoom: 16 // 缩放级别
      }) // 新照相机的位置
      this.mapController?.moveCamera(cameraUpdate)

      // 看到具体的位置
      // 利用花瓣地图的浮层
      this.mapController?.addMarker({
        position: {
          longitude: result.longitude,
          latitude: result.latitude
        },
        title: '您当前的位置',
        clickable: true
      })
      // 在以定位的位置画个圈
      this.mapController?.addCircle({
        radius: 500,
        center: {
          longitude: result.longitude,
          latitude: result.latitude
        },
        fillColor: 0XFF00FFFF
      })
      // 要拿经纬度点的具体的街道位置
      const res = await geoLocationManager.getAddressesFromLocation({
        latitude: result.latitude,
        longitude: result.longitude
      })
      if(res.length) {
       this.currentAddress = res[0].placeName as string
      }

    } catch (error) {
      AlertDialog.show({ message: error.message })
    }
  }

  build() {
    MapComponent({
      mapOptions: this.mapOption,
      mapCallback: this.callback // 地图初始化完成 会调用回调函数
    })
      .width('100%')
      .height("100%")
  }
}

export default Location
```

+ 发送位置

```typescript
  // 获取位置
  @Builder
  getLocation () {
    // 放置地图组件
    Stack({ alignContent: Alignment.Top }) {
      Location({ currentAddress: $currentAddress })
      Row() {
        Text("取消")
          .fontColor($r("app.color.text_second"))
          .onClick(() => {
            this.showLocation = false
            this.currentAddress = ""
          })
        Button("确认")
          .type(ButtonType.Normal)
          .borderRadius(4)
          .backgroundColor($r("app.color.primary"))
          .height(30)
          .width(60)
          .onClick(() => {
            // 拿到子组件的值
            // 将这个值传递发送消息
            if(this.currentAddress) {
              // 发送消息
              this.sendTextMessage(this.currentAddress)
            }
            this.currentAddress = ""
            this.showLocation = false
          })
      }
      .justifyContent(FlexAlign.SpaceBetween)
      .width('100%')
      .padding({
        left: 20,
        right: 20
      })
      .height(60)
      .margin({
        top: 50
      })
    }

  }
```

:::color1
提交代码

:::

<h1 id="hi7t1">语音转化</h1>
:::color2
需要注意： 只能支持真机，只能支持采样率为16000赫兹的pcm音频识别

:::

+ AudioCaputur/AudioRenderer 都要换成16000赫兹

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712995802255-51970ecc-7c9d-4829-81c7-b7887efea99b.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_26%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color2
当语音划到右侧时，进行语音转化

:::

```typescript
import { BusinessError } from '@ohos.base';
import { speechRecognizer, textToSpeech } from '@kit.CoreSpeechKit';
import { util } from '@kit.ArkTS';
import fileIo from '@ohos.file.fs';
import { promptAction } from '@kit.ArkUI';

export class VoiceTransfer {
  // 语音识别成文字
  private static asrEngine: speechRecognizer.SpeechRecognitionEngine;
  // 文字转语音
  private static ttsEngine: textToSpeech.TextToSpeechEngine
  private static voiceExtraParam: Record<string, Object> = {
    "style": 'interaction-broadcast',
    "locate": 'CN',
    "name": 'EngineName'
  };
  private static voiceInitParamsInfo: textToSpeech.CreateEngineParams = {
    language: 'zh-CN',
    person: 0,
    online: 1,
    extraParams: VoiceTransfer.voiceExtraParam
  };

  // 文本转语音
  static async textToVoice(speakText: string) {
    if (!VoiceTransfer.ttsEngine) {
      // 文本转语音引擎创建
      VoiceTransfer.ttsEngine = await textToSpeech.createEngine(VoiceTransfer.voiceInitParamsInfo)
    }
    let extraParam: Record<string, Object> = {
      "speed": 1,
      "volume": 1,
      "pitch": 1,
      "languageContext": 'zh-CN',
      "audioType": "pcm"
    }
    let speakParams: textToSpeech.SpeakParams = {
      requestId: util.generateRandomUUID(),
      extraParams: extraParam
    }
    VoiceTransfer.ttsEngine.speak(speakText, speakParams)
  }

  // 设置创建引擎参数
  private static textExtraParams: Record<string, Object> = { "locate": "CN", "recognizerMode": "short" }
  private static textInitParamsInfo: speechRecognizer.CreateEngineParams = {
    language: 'zh-CN',
    online: 1,
    extraParams: VoiceTransfer.textExtraParams
  };
  private static sessionId: string = "" // 会话id
  static async VoiceToText(path: string, call: (result: speechRecognizer.SpeechRecognitionResult) => void) {
    try {
      if (!VoiceTransfer.asrEngine) {
        VoiceTransfer.asrEngine = await speechRecognizer.createEngine(VoiceTransfer.textInitParamsInfo)
      }
      if (VoiceTransfer.asrEngine.isBusy()) return // 说明正在识别不用处理a
      // 创建回调对象
      let setListener: speechRecognizer.RecognitionListener = {
        // 开始识别成功回调
        onStart(sessionId: string, eventMessage: string) {
          console.info("onStart sessionId: " + sessionId + "eventMessage: " + eventMessage);
        },
        // 事件回调
        onEvent(sessionId: string, eventCode: number, eventMessage: string) {
          console.info("onEvent sessionId: " + sessionId + "eventCode: " + eventCode + "eventMessage: " + eventMessage);
        },
        // 识别结果回调，包括中间结果和最终结果
        onResult(sessionId: string, result: speechRecognizer.SpeechRecognitionResult) {
          call(result) // 返回语音识别内容
          if(result.isLast) {
            VoiceTransfer.asrEngine.finish(sessionId) // 结束
          }
        },
        // 识别完成回调
        onComplete(sessionId: string, eventMessage: string) {
          // VoiceTransfer.asrEngine.finish(sessionId) // 结束
          console.info("onComplete sessionId: " + sessionId + "eventMessage: " + eventMessage);

        },
        // 错误回调，错误码通过本方法返回
        // 返回错误码1002200002，开始识别失败，重复启动startListening方法时触发
        // 更多错误码请参考错误码参考
        onError(sessionId: string, errorCode: number, errorMessage: string) {
          console.error("onError sessionId: " + sessionId + "errorCode: " + errorCode + "errorMessage: " + errorMessage);
        },
      }
      // 设置回调
      VoiceTransfer.asrEngine.setListener(setListener);

      let audioParam: speechRecognizer.AudioInfo = {
        audioType: 'pcm',
        sampleRate: 16000,
        soundChannel: 1,
        sampleBit: 16
      };
      let extraParam: Record<string, Object> = { "vadBegin": 2000, "vadEnd": 3000, "maxAudioDuration": 60000 };
      let recognizerParams: speechRecognizer.StartParams = {
        sessionId: util.generateRandomUUID(),
        audioInfo: audioParam,
        extraParams: extraParam
      };
      VoiceTransfer.sessionId = recognizerParams.sessionId
      // 调用开始识别方法
      VoiceTransfer.asrEngine.startListening(recognizerParams);
      VoiceTransfer.writeAudio(path)
    } catch (error) {
      // AlertDialog.show({
      //   message: JSON.stringify(error)
      // })
    }

  }

  // 写音频流
  static async writeAudio(path: string) {

    let file = fileIo.openSync(path, fileIo.OpenMode.READ_WRITE); // 读文件
    // let stat = fileIo.statSync(file.fd)
    try {
      let buf: ArrayBuffer = new ArrayBuffer(1280);
      let totalSize: number = 0
      while (totalSize < fileIo.statSync(file.fd).size)  {
         fileIo.readSync(file.fd, buf, {
           offset: totalSize,
           length: 1280
         })
        let unit8Array: Uint8Array = new Uint8Array(buf);
        VoiceTransfer.asrEngine.writeAudio(VoiceTransfer.sessionId, unit8Array);
        // 这里必须加延迟才可以
        await new Promise<boolean>((resolve) => {
          setTimeout(() => resolve(true), 40)
        })
        // 延迟时间
        totalSize = totalSize + 1280;
      }
    } catch (e) {
      console.error("read file error " + e);
    } finally {
      fileIo.closeSync(file)
      VoiceTransfer.stopTransfer()
    }
  }
  // 停止转换文字
  static async stopTransfer() {
    if (VoiceTransfer.asrEngine && VoiceTransfer.asrEngine.isBusy() && VoiceTransfer.sessionId) {
      VoiceTransfer.asrEngine.finish(VoiceTransfer.sessionId)
    }
  }
}
```

+ 当拖入到右侧转化时处理

```typescript
PanGesture()
                  .onActionUpdate((event) => {
                    // 取消
                    if (event.fingerList[0].globalY > this.screenHeight - 120) {
                      // 表示没有出去录音区
                      this.voiceState = VoiceRecordEnum.RecordIng
                    } else {
                      // 表示出去了
                      if (event.fingerList[0].globalX < this.screenWidth / 2) {
                        this.voiceState = VoiceRecordEnum.Cancel
                      } else {
                        this.voiceState = VoiceRecordEnum.Transfer
                        // 如果是转化文本类
                        VoiceTransfer.VoiceToText(this.tempAudioPath, (res) => {
                           this.asrResult = res.result
                        })
                      }
                    }

                  })
```

+ 在VoiceInput中显示

```typescript
  @Consume
  asrResult: string

 if(this.voiceState === VoiceRecordEnum.Transfer) {
      Row(){
        Text(this.asrResult)
          .fontSize(20)
          .fontColor($r("app.color.text_primary"))
        }
        .alignItems(VerticalAlign.Top)
        .padding(10)
        .height(120)
        .width(280)
        .borderRadius(20)
        .backgroundColor($r('app.color.chat_primary'))
    }
```

+ 在松手逻辑中处理转化文本

```typescript
// 松手判断逻辑
  releaseFinger() {
    this.showVoiceCom = false
    this.stopCollectVoice() // 先关闭录音
    VoiceTransfer.stopTransfer()
    if (this.voiceState === VoiceRecordEnum.Cancel) {
      // 如果松手时，是取消状态 不管录的语音怎么样 直接删除
      this.duration = 0
      FileCommon.delFilePath(this.tempAudioPath) // 删除路径
    } else if (this.voiceState === VoiceRecordEnum.Transfer) {
       this.duration = 0
       if(this.asrResult) {
         this.sendTextMessage(this.asrResult)
       }
    }
    else if (this.voiceState === VoiceRecordEnum.RecordIng) {
      // 如果是正常录音 发送语音信息
      this.sendAudio()
    }
    this.voiceState = VoiceRecordEnum.RecordIng
    this.asrResult = "" // 设置为空
  }
```

:::color2
提交代码

:::

<h1 id="LoDc5">浮动菜单转化语音为文本</h1>
:::color2
当消息是音频时，将其转化为文本显示在下方

:::

+ 判断消息类型，点击转文字转化

```typescript
{
      title: '转文字',
      icon: $r("app.media.ic_public_trans_text"),
      itemClick: () => {
        if(this.currentMessage.messageType === MessageTypeEnum.AUDIO) {
          VoiceTransfer.VoiceToText(this.currentMessage.sourceFilePath, (res) => {
            this.transferResult = res.result
          })
        }
        this.showPopup = false
      }
    }
```

+ 在底部显示内容

```typescript
// 获取语音显示
  @Builder
  getAudioContent() {
    Column({ space: 10 }) {
      Row({ space: 5 }) {
        Text(`${this.currentMessage.sourceDuration}'`)
          .textAlign(TextAlign.Center)
        ImageAnimator()
          .images([
            {
              src: $r("app.media.ic_public_voice3")
            },
            {
              src: $r("app.media.ic_public_voice1")
            },
            {
              src: $r("app.media.ic_public_voice2")
            },
            {
              src: $r("app.media.ic_public_voice3")
            }
          ])
          .iterations(-1)
          .state(this.audioState)
          .width(20)
          .height(20)
          .rotate({
            angle: this.isOwnMessage ? 180 : 0
          })
      }
      .width(this.getAudioWidth())
      .backgroundColor(this.isOwnMessage ? $r('app.color.chat_primary') : $r('app.color.white'))
      .justifyContent(this.isOwnMessage ? FlexAlign.End : FlexAlign.Start)
      .height(40)
      .padding({
        left: 10,
        right: 10
      })
      .margin({
        left: 10,
        right: 10
      })
      .borderRadius(4)
      .direction(this.isOwnMessage ? Direction.Ltr : Direction.Rtl)
      .onClick(() => {
        AudioRenderer.start(this.currentMessage.sourceFilePath, () => {
          this.audioState = AnimationStatus.Stopped
        })
        this.audioState = AnimationStatus.Running
      })
      if(this.transferResult) {
        Text(this.transferResult)
          .backgroundColor(this.isOwnMessage ? $r('app.color.second_primary') : $r('app.color.white'))
          .fontColor($r('app.color.text_primary'))
          .padding(10)
          .lineHeight(24)
          .margin({
            left: 10,
            right: 10
          })
          .borderRadius(5)
      }
    }.alignItems(this.isOwnMessage ? HorizontalAlign.End : HorizontalAlign.Start)

  }
```

:::color2
提交代码

:::



<h1 id="NzJvV">将机器人返回文本用AI小艺播放出来</h1>
:::color2
在原有语音转文本的基础上，添加文本转语音的方法和属性

:::

```typescript
export class VoiceTransfer {
  // 文字转语音
  private static ttsEngine: textToSpeech.TextToSpeechEngine
  private static voiceExtraParam: Record<string, Object> = {
    "style": 'interaction-broadcast',
    "locate": 'CN',
    "name": 'EngineName'
  };
  private static voiceInitParamsInfo: textToSpeech.CreateEngineParams = {
    language: 'zh-CN',
    person: 0,
    online: 1,
    extraParams: VoiceTransfer.voiceExtraParam
  };

  // 文本转语音
  static async textToVoice(speakText: string) {
    if (!VoiceTransfer.ttsEngine) {
      // 文本转语音引擎创建
      VoiceTransfer.ttsEngine = await textToSpeech.createEngine(VoiceTransfer.voiceInitParamsInfo)
    }
    let extraParam: Record<string, Object> = {
      "speed": 1,
      "volume": 1,
      "pitch": 1,
      "languageContext": 'zh-CN',
      "audioType": "pcm"
    }
    let speakParams: textToSpeech.SpeakParams = {
      requestId: util.generateRandomUUID(),
      extraParams: extraParam
    }
    VoiceTransfer.ttsEngine.speak(speakText, speakParams)
  }

}
```

:::color2
当对方返回文本时，用语音播放出来

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1712495123522-dcf1a1b0-12eb-48e6-a1b6-965d6b99a9bc.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_48%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



<h1 id="JAlp4">计算显示语音波峰</h1>
:::color2
当长按语音时，输出波峰动画

:::

+ 使用线程通信(录音时输出波段buffer)

```typescript
emitter.emit("onBuffer", { data: { buffer } })
```

+ voiceInput监听buffer

```typescript
aboutToAppear(): void {
   emitter.on("onBuffer", (res: emitter.EventData) => {
     this.calculateAmplitudes(res.data!["buffer"] as ArrayBuffer)
   })
  }
```

+ 卸载时解除订阅

```typescript
 aboutToDisappear(): void {
    emitter.off("onBuffer")
  }
```

+ 声明变量记录振幅

```typescript
  @State
  list: number[] = []
```

+ 计算振幅

```typescript
 // 计算波峰
  calculateAmplitudes(buffer: ArrayBuffer) {
    try {
      const sampleSize = Math.floor(buffer.byteLength / 20); // 计算每个均分区间的大小
      const view = new DataView(buffer);
      const amplitudes: number[] = [];
      // 遍历缓冲区，计算每个样本的振幅并转换为高度
      // 遍历原始缓冲区，提取每个均分区间的振幅
      for (let i = 0; i < buffer.byteLength; i += sampleSize) {
        let sum = 0;
        // 计算当前均分区间内所有振幅的平均值
        for (let j = i; j < i + sampleSize; j += 2) { // 假设每个样本占据 2 字节
          const sample = view.getInt16(j, true);
          sum += Math.abs(sample);
        }
        const averageAmplitude = 150 * sum / (sampleSize / 2) / 32767 ; // 假设每个样本占据 2 字节
        amplitudes.push(averageAmplitude < 10 ? 10: averageAmplitude );
      }
      animateTo({ duration: 100 }, () => {
        this.list = amplitudes
      })

    }catch (error) {
      AlertDialog.show({ message: error.message })
    }
  }
```

+ 根据振幅显示内容

```typescript
 if (this.voiceState === VoiceRecordEnum.RecordIng) {
      Row({ space:2 }) {
        ForEach(this.list, (v: number) => {
           Row()
             .height(v)
             .width(2)
             .borderRadius(1)
             .backgroundColor($r("app.color.animate_voice_color"))
        })
      }
      .justifyContent(FlexAlign.Center)
      .height(80)
      .width(180)
      .borderRadius(20)
      .backgroundColor($r('app.color.chat_primary'))
    }
```

:::color2
提交代码

:::

<h1 id="qvgYI">主页顶部下拉菜单</h1>
:::color1
在顶部增加一个搜索和下拉菜单

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708331145582-c2280aee-48f5-4301-bf3e-4116a667bd23.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 定义下拉的数据选项

```typescript
@State
  popList: PopupItem[] = [
    {
      title: '发起群聊',
      icon: $r('app.media.ic_public_message')
    },
    {
      title: '添加朋友',
      icon: $r('app.media.ic_public_add_friend')
    },
    {
      title: '扫一扫',
      icon: $r('app.media.ic_public_scan')
    },
    {
      title: '收付款',
      icon: $r('app.media.ic_public_receive')
    }
  ]
```

+ 根据数据实现一个下拉的builder

```typescript
@Builder
  getDropDown() {
    Column() {
      ForEach(this.popList, (item: PopupItem) => {
        Row({ space: 5 }) {
          Image(item.icon)
            .fillColor($r('app.color.white'))
            .width(20)
            .height(20)
          Text(item.title)
            .fontColor(Color.White)
            .layoutWeight(1)
            .textAlign(TextAlign.Center)
        }
        .width('100%')
        .height(48)
        .justifyContent(FlexAlign.Center)
        .padding({
          left: 10,
          right: 10
        }).onClick(() => {
          item.itemClick && item.itemClick()
        })

      })
    }
    .width(120)
  }
```

+ 定义控制下拉的属性

```typescript
  @State
  showDropDown: boolean = false // 显示底部浮层
```

+ 绑定bindPopup属性

```typescript
 Row() {
        Text(`微信(${this.list.length})`)
          .fontSize(16)
          .fontColor($r('app.color.text_primary'))
        Image($r('app.media.ic_public_add_norm'))
          .width(20)
          .height(20)
          .fillColor($r('app.color.text_primary'))
          .position({
            x: '100%'
          })
          .translate({
            x: -40,
            y: 15
          })
          .bindPopup(this.showDropDown, {
            builder: this.getDropDown,
            placement: Placement.Bottom,
            onStateChange: (event) => {
              this.showDropDown = event.isVisible
            },
            popupColor: $r("app.color.popup_back"),
            backgroundBlurStyle: BlurStyle.NONE
          })
          .onClick(() => {
            this.showDropDown = true
          })

      }.width('100%')
      .justifyContent(FlexAlign.Center)
      .height(50)
```

:::color1
提交代码

:::

<h1 id="KBcNC">扫码功能</h1>
+ 注册点击事件

```typescript
 {
      title: '扫一扫',
      icon: $r('app.media.ic_public_scan'),
      itemClick: () => {
        this.scan() // 扫码
      }
    },
```

+ 定义扫码方法

```typescript
 // 扫码
  async scan() {
    // 定义扫码参数options
    let options: scanBarcode.ScanOptions = {
      scanTypes: [scanCore.ScanType.ALL],
      enableMultiMode: true,
      enableAlbum: true
    };
    // 启动扫码，拉起扫码界面
    try {
      const result = await scanBarcode.startScanForResult(getContext(this), options)
    } catch (error) {
      promptAction.showToast({ message: error.message })
    }
  }
```



<h1 id="eUU7r">实现收付款页面</h1>
:::info
点击收付款生成一个二维码

:::

+ 注册收付款点击事件-跳转到收付款页面

```typescript
  {
      title: '收付款',
      icon: $r('app.media.ic_public_receive'),
      itemClick: () => {
         router.pushUrl({
           url: 'pages/PayQrCode/PayQrCode'
         })
      }
    }
```

+ 创建一个收付款页面 pages/PayQrCode/PayQrCode.ets

```typescript
import { router } from '@kit.ArkUI'

@Entry
@Component
struct PayQrCode {
  build() {
    Column() {
      Row() {
        Stack({ alignContent: Alignment.Start }) {
          Image($r('app.media.ic_public_arrow_left'))
            .width(30)
            .height(30)
            .fillColor($r("app.color.white"))
            .onClick(() => {
              router.back()
            })
            .zIndex(2)

          Text("收付款")
            .width('100%')
            .textAlign(TextAlign.Center)
            .fontSize(16)
            .fontColor($r('app.color.white'))
        }
        .height(50)
      }
      .padding({
        left: 10,
        right: 10
      })

      Row() {
        Column() {
          Row({ space: 10 }) {
            Image($r("app.media.ic_public_scan"))
              .width(20)
              .height(20)
              .fillColor($r("app.color.pay_back"))
            Text("付款码")
              .fontColor($r("app.color.pay_back"))
          }
          .width('100%')
          .justifyContent(FlexAlign.Start)
          .height(60)
          .border({
            width: {
              bottom: 0.5
            },
            color: $r("app.color.border_color")
          })

          // 显示码
          Column({ space: 20 }) {
            Text("优先使用xx银行储蓄卡付款")
              .fontColor($r("app.color.text_second"))
              .fontSize(12)
          }
          .margin({
            top: 10,
            bottom: 10
          })
        }
        .padding(10)
        .borderRadius(4)
        .width("100%")
        .backgroundColor($r("app.color.white"))
      }
      .padding({
        left: 10,
        right: 20
      })

    }
    .width('100%')
    .height('100%')
    .backgroundColor($r("app.color.pay_back"))
  }
}

```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708333185972-e0e3d452-f57b-40ac-965e-cdec44fdc120.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



:::color1
提交代码

:::



<h1 id="OouaO">生成条形码和二维码</h1>
:::color1
+ 随机生成一个基于当前用户的随机数
+ 使用二维码组件显示二维码
+ 使用生成条形码工具生成条形码
+ 30秒一刷新对应的码

:::

+ 定义一个二维码的随机数

```typescript
@State
  payParams: string = Math.random().toString()
```

+ 十秒随机生成随机数

```typescript
@State
  payParams: string = Math.random().toString()
  timer: number = -1
  @State
  barCodeImage: PixelMap | null = null
  aboutToAppear(): void {
    this.createQrCodeValue()
    this.createBarCode()
  }
  aboutToDisappear(): void {
    clearTimeout(this.timer)
  }
  createQrCodeValue () {
    this.timer = setTimeout(async () => {
      this.payParams = Math.random().toString()
    }, 10000)
  }
```

+ 使用二维码组件显示

```typescript
  QRCode(this.payParams)
              .width(140)
              .height(140)
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708335402735-7661832d-8637-4752-b1f3-a0ac3ed16bcf.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_15%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

+ 使用二维码生成工具生成条形码

:::danger
模拟器不可用-待解决

:::

+ 定义一个状态接收PixelMap

```typescript
  @State
  barCodeImage: PixelMap | null = null
```

+ 定义生成条形码方法

```typescript
// 创建条形码
  async createBarCode() {
    let options: generateBarcode.CreateOptions = {
      scanType: scanCore.ScanType.CODE128_CODE,
      height: 200,
      width: 800
    }
    // 码图生成接口，成功返回PixelMap格式图片
    this.barCodeImage = await generateBarcode.createBarcode(this.payParams, options)
  }
```

+ 显示条形码

```typescript
  Image(this.barCodeImage)
              .width(280)
              .height(100)
              .objectFit(ImageFit.Contain)
```

+ 在初始化时生成

```typescript
aboutToAppear(): void {
    this.createQrCodeValue()
    this.createBarCode()
  }
```

+ 10秒后更新

```typescript
createQrCodeValue () {
    this.timer = setTimeout(async () => {
      this.payParams = Math.random().toString()
      this.createBarCode()
    }, 10000)
  }
```



:::color1
提交代码

:::

<h1 id="dz8ll">我的页面结构</h1>
:::color1
实现我的页面结构

:::

```typescript
@Preview
@Component
struct My {
  @Builder
  getRenderItem (left: string, rightClick?: () => void) {
    Row() {
      Text(left)
      Image($r("app.media.ic_public_right"))
        .width(16)
        .height(16)
    }
    .width('100%')
    .padding({
      left: 20,
      right: 20
    })
    .backgroundColor($r("app.color.white"))
    .height(60)
    .justifyContent(FlexAlign.SpaceBetween)
    .border({
      color: $r("app.color.border_color"),
      width: {
        bottom: 0.5
      }
    })
  }
  build() {
    Column() {
      // 顶部
      Row () {
        Row({ space: 10 }) {
          Image("https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fsafe-img.xhscdn.com%2Fbw1%2Fea86243a-a102-49d3-90e5-f48d3b909b94%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fsafe-img.xhscdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1710934156&t=5f402de56ae39dbfc8f1ba8e0af465a2")
            .width(60)
            .height(60)
            .borderRadius(6)
          Column({ space: 10 }) {
            Text("老高").fontSize(18).fontColor($r('app.color.text_primary'))
            Text("微信号：4334343").fontColor($r('app.color.text_second')).fontSize(14)
          }.alignItems(HorizontalAlign.Start)
        }
        .layoutWeight(1)
        Image($r("app.media.ic_public_right"))
          .width(16)
          .height(16)
          .fillColor($r('app.color.text_second'))
      }
      .justifyContent(FlexAlign.SpaceBetween)
      .padding(30)
      .width('100%')
      .backgroundColor($r("app.color.white"))
      Row().height(10)
      this.getRenderItem("服务")
      Row().height(10)
      this.getRenderItem("收藏")
      this.getRenderItem("朋友圈")
      this.getRenderItem("卡包")
      this.getRenderItem("表情")
      Row().height(10)
      this.getRenderItem("设置")
    }
    .width('100%')
    .height('100%')
    .backgroundColor($r('app.color.back_color'))
  }
}
export default My
```

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708342771942-f4b4bbe6-2aa7-4a3c-8e10-436b96c79a16.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_11%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
在主页中显示该组件

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708342860147-db053fa7-c5c7-479d-85d0-139b5cf994d9.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_22%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)



+ 将我的页面的数据变成当前的用户信息

```typescript
@StorageProp(WeChat_CurrentUserKey)
  currentUser: UserInfoModel = new UserInfoModel({} as UserInfo)
  
```

+ 渲染页面

```typescript
Row({ space: 10 }) {
          Image(this.currentUser.avatar)
            .width(60)
            .height(60)
            .borderRadius(6)
          Column({ space: 10 }) {
            Text(this.currentUser.username).fontSize(18).fontColor($r('app.color.text_primary'))
            Text(`微信号：${this.currentUser.user_id}`).fontColor($r('app.color.text_second')).fontSize(14)
          }.alignItems(HorizontalAlign.Start)
        }
        .layoutWeight(1)
```

:::color1
提交代码

:::

<h1 id="fQ71U">发现页面结构</h1>
:::color1
新建pages/Find/Find.ets

:::

```typescript

@Preview
@Component
struct Find {
  

  @Builder
  getRenderItem(left: string, rightClick?: () => void) {
    Row() {
      Text(left)
      Image($r("app.media.ic_public_right"))
        .width(16)
        .height(16)
    }
    .width('100%')
    .padding({
      left: 20,
      right: 20
    })
    .backgroundColor($r("app.color.white"))
    .height(60)
    .justifyContent(FlexAlign.SpaceBetween)
    .border({
      color: $r("app.color.border_color"),
      width: {
        bottom: 0.5
      }
    })
  }

  build() {
    Column() {
      Row() {
        Text("发现")
      }
      .justifyContent(FlexAlign.Center)
      .height(40)
      .width('100%')
      Scroll() {
        Column() {
          // 顶部
          this.getRenderItem("朋友圈")
          Row().height(10)
          this.getRenderItem("视频号")
          this.getRenderItem("直播")
          Row().height(10)
          this.getRenderItem("扫一扫")
          this.getRenderItem("摇一摇")
          Row().height(10)
          this.getRenderItem("看一看")
          this.getRenderItem("搜一搜")
          Row().height(10)
          this.getRenderItem("附近")
          Row().height(10)
          this.getRenderItem("购物")
          this.getRenderItem("游戏")
          Row().height(10)
          this.getRenderItem("小程序")
          Row().height(10)
        }
      }
    }
    .width('100%')
    .height('100%')
    .backgroundColor($r('app.color.back_color'))
  }
}

export default Find
```

:::color1
在主页中显示该组件

:::

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708343900447-247f6c94-86cb-4cf7-86ce-bc1813275053.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_10%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

![](https://cdn.nlark.com/yuque/0/2024/png/8435673/1708343971617-37bdfbde-8573-4009-bb1e-46c974afee72.png?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_21%2Ctext_6buR6ams56iL5bqP5ZGY%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10)

:::color1
提交代码

:::



