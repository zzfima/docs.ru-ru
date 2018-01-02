---
title: "&lt;Очистить&gt; элемент для &lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e48887cf7e227f463b92edd50f69746bbd8abd0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-configsections"></a>\<Очистить > элемент для \<configSections >

Удаляет все ранее определенные разделы и группы разделов.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Очистить >**

## <a name="syntax"></a>Синтаксис

```xml
<clear/>
```

## <a name="attribute"></a>Атрибут

|           | Описание: |
| --------- | ----------- |
| **name**  | Обязательный атрибут.<br><br>Задает имя раздела или группы разделов. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание: |
| --- | ----------- |
| [**\<configSections >** элемент](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Содержит раздел конфигурации и пространства имен объявления. |

# <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="remarks"></a>Примечания

 **\<Снимите >** элемент удаляет все разделы и группы разделов приложения, определенные ранее в текущем файле конфигурации или на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В этом примере определяется в файле конфигурации компьютера и файл конфигурации приложения и показано, как использовать  **\<снимите >** элемент в файле конфигурации приложения для очистки разделов, ранее определенные в файл конфигурации компьютера.

В коде следующего файла конфигурации компьютера объявляются два раздела  **\<sampleSection >** и  **\<anotherSampleSection >**, которые считываются до применения файл конфигурации:

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

В коде следующего файла конфигурации приложения Очистка всех ранее определенных разделов. Приложение не может использовать или извлекать параметры из разделов, которые были объявлены в файле конфигурации компьютера. Тем не менее, можно использовать параметры из  **\<anotherSection >** , так как он следует после  **\<снимите >** элемента.

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

Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.

## <a name="see-also"></a>См. также

[Схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
