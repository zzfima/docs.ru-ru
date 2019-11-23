---
title: Настраиваемый элемент для Синглетагсектионхандлер
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac2d01121e81b545556fb082fa7b82c31cccf9da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118834"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Настраиваемый элемент для Синглетагсектионхандлер

Определяет параметры в пользовательском разделе конфигурации, определяемом \<разделе > элемента и использующем класс <xref:System.Configuration.SingleTagSectionHandler>.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName >*

## <a name="syntax"></a>Синтаксис

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Атрибуты

Атрибуты и значения атрибутов определяются пользователем.

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="remarks"></a>Примечания

Элемент **\<sectionName >** — это пользовательский элемент, определяемый тегом [ **\<раздела >** ](section-element.md) в элементе [ **\<configSections >** ](configsections-element-for-configuration.md) . Система конфигурации возвращает объект <xref:System.Collections.IDictionary> при вызове <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем примере объявляется пользовательский элемент с именем **\<самплесектион >** , который содержит параметры, считанные классом <xref:System.Configuration.SingleTagSectionHandler>:

```xml
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

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также:

- [Схема файла конфигурации для .NET Framework](index.md)
