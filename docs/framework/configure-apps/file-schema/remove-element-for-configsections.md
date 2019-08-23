---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4ff9bb537a31e28dbd4b878c1bc04c96262f85ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927459"
---
# <a name="remove-element-for-configsections"></a>\<Удаление элемента > для \<configSections >

Удаляет предопределенный раздел или группу разделов.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<> configSections**](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**

## <a name="syntax"></a>Синтаксис

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **name**  | Обязательный атрибут.<br><br>Указывает имя раздела или группы разделов, которые нужно удалить. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [элемент  **>\<configSections**](configsections-element-for-configuration.md) | Содержит раздел конфигурации и объявления пространств имен. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Примечания

Элемент  **\<Remove >** можно использовать для удаления разделов и групп разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В следующем примере показано,  **\<** как использовать элемент remove > в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации компьютера.

Следующий код файла конфигурации компьютера объявляет раздел  **\<самплесектион >** :

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

В следующем коде файла конфигурации приложения удаляется  **\<раздел > самплесектион** . После удаления приложение не сможет получить параметры в  **\<самплесектион >** .

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
