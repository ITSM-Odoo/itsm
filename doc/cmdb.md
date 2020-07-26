# cmdb

## configuration management database

涵盖的业务对象

- CI
- Relation
- Asset
- CI Asset Mapping

### 1. CI - configuration item

CI 是配置管理的基本对象，是配置对象的逻辑概念，通常，它具有类别 CLASS 以及属性 PROPERTIES，就跟面向对象编程概念里面的 类，对象，属性 一样。

- CI Class
- CI Class property
- CI
- CI property

#### 1.1 CI class

具备以下属性

- ID, required
- description, required
- parent CI class, required
- properties

CI Class 可以互相嵌套，下级具备上级的数据，但是可以改写为自身的。

#### 1.2. CI class property

具备以下属性

- ID, required
- description, required
- Value, required
- Value UoM
- children properties

属性也可以嵌套，下级继承修改上级的

#### 1.3. CI

具备以下属性

- ID, required
- description, required
- CI Class, required
- parent CI
- Children CI
- properties

#### 1.4. CI property

具备以下属性

- ID, required
- description, required
- Value, required
- Value UoM

#### 1.5. CI Relation

也就是 CI 之间的关系，这也是个逻辑概念，关系具有不同的类型，和任意可以添加的属性

具备以下属性

- CI ID, required
- CI ID, required
- relation type, required
- properties

CI 关系 存在一个 关系类型和关于关系的属性

relation type

具备以下属性

- ID
- description
- type, 枚举

relation property

具备以下属性

- ID, required
- description, required
- Value, required
- Value UoM

### 2. 资产 asset

asset 是物理概念，代表了实实在在的资产，例如 硬件，软件

具备以下属性

- ID
- description
- type
- vendor
- purchase date
- location
- asset Tag

### 3. CI 与 资产 asset 之间的 关系

CI 是逻辑概念，而 asset 则是物理概念； 他们之间存在 对应关系

具备以下属性

- CI ID
- Asset ID
- from date
- to date

### 4. config 配置

config 是配置项/或者设备 的运行配置，它是 运行代码和配置的总称，可以通过 CM 系统进行保存，然后通过 CM 进行差异比对

应当具有以下属性

- ID
- description
- CI
- config URL
- date
- difference 【 可能与 change 存在功能重叠】

配置与 配置项，设备之间的关系
