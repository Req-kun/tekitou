※適当に作ったモジュールのため、バグが発生する可能性があります。もしバグが発生した場合、Discord(Req van Astraea#9732)もしくはTwitter(@Req_fn)までご連絡ください。※

# install

```
pip install discord-embed-extensions
```

# import

```
import discord_embed_extensions
```

# 追加されるもの
## 追加される関数
> make - 指定された引数をもとにdiscord.Embedを作成し、返す  
author_dict - makeコマンド等でauthorを指定する時にdictの作成を補助する  
footer_dict - makeコマンド等でfooterを指定する時にdictの作成を補助する  
field_dict - makeコマンド等でfieldを指定する時にdictの作成を補助する  


## 追加されるメソッド
> edit - 指定された引数をもとにdiscord.Embed情報を編集する  
multiple_add_fields - 一度に複数のfieldを追加する  
multiple_remove_fields - 一度に複数のfieldを削除する


# 各関数、メソッドの使い方

## make()

```
discord_embed_extensions.make(**kwargs)
```  

**Attributes**  
> author  
color  
description  
fields  
footer  
image  
thumbnail  
title  
url  

### title
`title='title'`  
Type: str

### description
`description='description'`  
Type: str

### url
`url='url'`  
Type: str

### color
`color=color`  
Type: Union[Colour, int]

### footer
`footer={'text': 'text', 'icon_url': 'icon_url'}`  
`footer=footer_dict(*, text='text', icon_url='icon_url')`  
Parameters  
・text(str)  
・icon_url(str)

### image
`image='url'`  
Type: str

### thumbnail
`thumbnail='url'`  
Type: str

### author
`author={'name': 'name', 'url': 'url', 'icon_url': 'icon_url'}`  
`author=author_dict(*, name='name', url='url', icon_url='icon_url')`  
Parameters  
・name(str)  
・url(str)  
・icon_url(str)

### fields
`fields=[{'name': 'name', 'value': 'value', 'inline': bool}, {'name': 'name', 'value': 'value', 'inline': bool}]`  
`fields=[field_dict(*, name='name', value='value', inline=bool), field_dict(*, name='name', value='value', inline=bool)]`  
Parameters  
・name(str)  
・value(str)  
・inline(bool) - default: True  

## author_dict()

```
author = discord_embed_extensions.author_dict(**kwargs)
```

**Attributes**  
> name  
url  
icon_url

### name
`name='name'`  
Type: str

### url
`url='url'`  
Type: str

### icon_url
`icon_url='icon_url'`  
Type: str

## footer_dict()

```
footer = discord_embed_extensions.footer_dict(**kwargs)
```  

**Attributes**  
> text  
icon_url

### text
`text='text'`  
Type: str

### icon_url
`icon_url='icon_url'`  
Type: str

## field_dict()

```
field = discord_embed_extensions.field_dict(**kwargs)
```  

**Attributes**  
> name  
value  
inline

### name
`name='name'`  
Type: str

### value
`value='value'`  
Type: str

### inline
`inline=[True / False]`  
Type: bool

## edit()

```
discord.Embed.edit(**kwargs)
```  

**Attributes**  
> author  
color  
description  
footer  
image  
thumbnail  
title  
url  

### title
`title='title'`  
Type: str

### description
`description='description'`  
Type: str

### url
`url='url'`  
Type: str

### color
`color=color`  
Type: Union[Colour, int]

### footer
`footer={'text': 'text', 'icon_url': 'icon_url'}`  
`footer=footer_dict(*, text='text', icon_url='icon_url')`  
Parameters  
・text(str)  
・icon_url(str)

### image
`image='url'`  
Type: str

### thumbnail
`thumbnail='url'`  
Type: str

### author
`author={'name': 'name', 'url': 'url', 'icon_url': 'icon_url'}`  
`author=author_dict(*, name='name', url='url', icon_url='icon_url')`  
Parameters  
・name(str)  
・url(str)  
・icon_url(str)

## multiple_add_fields()

```
discord.Embed.multiple_add_fields(fields)
```

Parameters  
　fields(dict in list) - makeコマンドと同じ指定方法

`.multiple_add_fields([{'name': 'name', 'value': 'value', 'inline': bool}, {'name': 'name', 'value': 'value', 'inline': bool}])`
`.multiple_add_fields([field_dict(*, name='name', value='value', inline=bool), field_dict(*, name='name', value='value', inline=bool)])`

## multiple_remove_fields()

インデックスの大きいほうから削除されていくため、インデックスの補完について考える必要はありません

```
discord.Embed.multiple_remove_fields(indexes)
```

Parameters
　indexes(list) - 要素はすべてint、順不同

`.multiple_remove_fields([2, 4, 3, 1])`
