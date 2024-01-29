# 物品

Before you start configuring the plugin itemstack make sure you are using the correct material for your version of the game.

Each button must be accompanied by an itemstack (except in certain specific cases).

```yaml
item:
  material: <材料>
  amount: <数量>
  data: <数据, only avaible between 1.8 and 1.12>
  durability: <durability>
  url: <player skin in base64>
  name: <display name>
  lore: <list of text>
  potion: <potion effect type>
  level: <potion level>
  sphash: <potion splash true or false>
  extended: <potion extended true of flase>
  glow: <add glow effect>
  modelID: <custom model id>
  enchants: <list of enchantments>
  flags: <list of itemflag>
  firework: <firework meta>
  banner: <banner color>
  patterns: <banner pattern>
  color: <leather armor color>
```

## 材料

```yaml
material: <材质>
```

物品的材料。 你可以使用一个占位符来显示一个材料。

> **支持的材料:**
>
> * [Material](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html) - 示例: `material: STONE`
> * [Placeholder](https://www.spigotmc.org/resources/placeholderapi.6245/) value - 示例: `material: %your_placeholder_material%`
> * [HeadDatabase](https://www.spigotmc.org/resources/head-database.14280/) (hdb:\<ID>) 示例: `material: hdb:<ID>`
> * [Oraxen](https://www.spigotmc.org/resources/%E2%98%84%EF%B8%8F-oraxen-add-items-blocks-armors-hats-food-furnitures-plants-and-gui-1-18-1-20-1.72448/) (oraxen:\<item name>) 示例: `material: oraxen:<item name>`
> * [ItemAdder](https://www.spigotmc.org/resources/%E2%9C%A8itemsadder%E2%AD%90emotes-mobs-items-armors-hud-gui-emojis-blocks-wings-hats-liquids.73355/) (itemsadder:\<item name>) 示例: `material:` itemsadder`:<item name>`
> * [SlimeFun](https://github.com/Slimefun/Slimefun4) (slimefun:\<item name>) 示例: `material:` slimefun`:<item name>`
> * [Nova](https://github.com/xenondevs/Nova) (nova:\<item/block name>) 示例: `material: nova:<item/block name>`

***

## 数量

```yaml
amount: <数量>
```

物品堆的数量。 你可以使用一个占位符来动态设置物品堆的数量。

***

## 数据

```yaml
data: <数据，仅1.8-1.12可用>
```

材料数据，仅在1.8-1.12可用，默认为0

***

## 耐久

```yaml
durability: <耐久>
```

物品的耐久，默认为0.

***

## Url

```yaml
url: <玩家皮肤base64>
```

Allows to display a head with a url in base64. You can find the values of the heads on the site [minecraft-heads.com](https://minecraft-heads.com/).

You must take the content in "Value" of the category "Other":

![minecraft-heads.com 示例](../.gitbook/assets/base64.png)

示例

```yaml
url: "eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNjM3YjhhMzk4MzdiYzNkNThmMDljOGM2ZTUzOTYyZDMzZjlmYTBiNjUzOThhNzc5MzUzYWRlMWUxNDcxM2VmZiJ9fX0="
```

***

## 名称

```yaml
name: <显示名>
```

物品将会显示的名字。可以搭配PlaceholderAPI一起使用。

{% hint style="info" %}
如果你的服务器有Kyori Adventure这个依赖(Paper及其下游自带), 你可以使用[mini message格式](https://docs.adventure.kyori.net/minimessage/format.html).
{% endhint %}

***

## Lore

```yaml
lore:
  - <line1>
  - <line2>
  - <line3>
  - ...
```

允许物品显示lore。可以搭配PlaceholderAPI一起使用。

***

## 药水

```yaml
  potion: <药水效果类型>
  level: <药水等级, 1 或 2> # 默认为1
  splash: <potion splash true or false>
  extended: <potion extended true of flase>
```

Allows you to create a potion. Check potion effect type [here](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/potion/PotionType.html).

{% hint style="danger" %}
Warning, a potion cannot be extended and with a level 2
{% endhint %}

{% hint style="info" %}
```yml
# 在1.8-1.12中你需要这样做:
material: POTION
durability: 16454
```
{% endhint %}

***

## 发光

```yaml
glow: <true 或 false>
```

允许物品发光。 这会给物品添加一个随机附魔以及 HIDE\_ENCHANT （隐藏附魔）物品标志.

***

## 模型ID

```yaml
modelID: <自定义模型id>
```

允许你在物品上设置模型ID（对材质包有用）

***

## 附魔

```yaml
enchants:
  - <附魔名称>,<附魔等级>
```

允许你添加附魔, you have to put the name of the enchantment then the level of the enchantment, like this: `ENCHANT,ENCHANT_LEVEL` List of enchantments available: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html)

***

## 标志

```yaml
flags:
  - <标志 1>
  - <标志 2>
  - ...
```

标志列表： [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html)

***

## 颜色

```yaml
type: LEATHER_CHESTPLATE
color: 40,150,40 # RGB 颜色

# 使用ARGB的示例
color: 1,40,150,40 # ARGB 颜色(Alpha, RED, GREEN, BLUE)
```

给皮革装备设置RGB (Red, Green, Blue) 颜色. 格式:

<pre class="language-yaml"><code class="lang-yaml"><strong>color: &#x3C;red>,&#x3C;green>,&#x3C;blue>
</strong></code></pre>

你也可以添加Alpha值来拥有ARGB颜色：

<pre class="language-yaml"><code class="lang-yaml"><strong>color: &#x3C;alpha>,&#x3C;red>,&#x3C;green>,blue>
</strong></code></pre>

{% hint style="info" %}
这个颜色格式同样应用于烟花和旗帜 \
关于Color(颜色)类的Javadoc: [此处](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html#fromARGB\(int,int,int,int\)).
{% endhint %}

***

## 烟花

```yaml
type: FIREWORK
firework:
  star: true
  flicker: true
  trail: true
  type: BALL_LARGE
  colors:
    - 250,10,10 # RGB 或 ARGB
  fadeColors:
    - 250,10,250 # RGB 或 ARGB
```

烟花类型: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/FireworkEffect.Type.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/FireworkEffect.Type.html)

***

## 旗帜

```yaml
type: BANNER
banner: PINK # 旗帜颜色
patterns: # 旗帜花纹: <颜色>:<花纹>
  - RED:SQUARE_BOTTOM_LEFT
  - GREEN:STRIPE_LEFT
```

允许你创建一个旗帜。 花纹列表: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html)

