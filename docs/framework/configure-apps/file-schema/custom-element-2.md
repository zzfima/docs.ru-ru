---
title: Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921038"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler

Определяет параметры для пользовательских разделов конфигурации, <xref:System.Configuration.NameValueSectionHandler> использующих <xref:System.Configuration.DictionarySectionHandler> классы и.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<sectionName >**

## <a name="attributes"></a>Атрибуты

Отсутствуют

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| Добавьте > для и [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler>  | Добавляет настраиваемые параметры приложения. |
| Удалите > для и [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | Удаляет ранее определенный параметр. |
| очистить > для и [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | Удаляет все ранее определенные параметры в разделе. |

## <a name="remarks"></a>Примечания

**\<Параметра sectionName>** элемент является пользовательским элементом определяется **\<разделе>** тегом **\<configSections>** элемент.

В следующей таблице показан тип объекта, возвращаемого методом ConfigurationSettings. config для каждого обработчика раздела конфигурации:

| Обработчик раздела конфигурации                        | Возвращаемый тип                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Пример

В следующем примере показано, как объявить разделы, в <xref:System.Configuration.DictionarySectionHandler> которых <xref:System.Configuration.NameValueSectionHandler> используются классы и.

Первый настраиваемый элемент —  **\<диктионарисампле >** , который содержит <xref:System.Configuration.DictionarySectionHandler> параметры, считанные классом в `System.dll` сборке. Второй настраиваемый элемент —  **\<мисектион >** , который содержит <xref:System.Configuration.NameValueSectionHandler> параметры, считанные классом в `System.dll` сборке.

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
