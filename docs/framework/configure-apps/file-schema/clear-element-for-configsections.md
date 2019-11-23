---
title: Элемент <clear> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a45572d0dcb2737558e11f5c38ac2ccc338c754a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119088"
---
# <a name="clear-element-for-configsections"></a>\<очистить элемент > для \<configSections >

Удаляет все ранее определенные разделы и группы разделов.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>Синтаксис

```xml
<clear/>
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **name**  | Обязательный атрибут.<br><br>Указывает имя раздела или группы разделов, которые нужно удалить. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<configSections >** Дерев](configsections-element-for-configuration.md) | Содержит раздел конфигурации и объявления пространств имен. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="remarks"></a>Примечания

**\<Снимите>** элемент удаляет все разделы и группы разделов приложения, определенные ранее в текущем файле конфигурации или на более высоком уровне в иерархии файла конфигурации.

## <a name="example"></a>Пример

В этом примере определяются в файле конфигурации компьютера и файл конфигурации приложения и показано, как использовать **\<снимите>** элемент в файле конфигурации приложения для очистки разделов, определенных ранее в файл конфигурации компьютера.

В следующем коде файла конфигурации компьютера объявляются два раздела: **\<самплесектион >** и **\<аносерсамплесектион >** , которые считываются до файла конфигурации приложения.

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

В следующем коде файла конфигурации приложения очищаются все ранее объявленные разделы. Приложение не может использовать или извлекать параметры в одном из разделов, объявленных в файле конфигурации компьютера. Тем не менее, его можно использовать параметры из **\<anotherSection>** потому, что он следует после **\<снимите>** элемент.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также:

- [Схема файла конфигурации для .NET Framework](index.md)
