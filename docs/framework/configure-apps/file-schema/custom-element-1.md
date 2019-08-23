---
title: Настраиваемый элемент для Синглетагсектионхандлер
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927504"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Настраиваемый элемент для Синглетагсектионхандлер

Определяет параметры в разделе пользовательской конфигурации, который определяется по \<разделу > элементу и <xref:System.Configuration.SingleTagSectionHandler> использует класс.

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

None

## <a name="remarks"></a>Примечания

Элемент > [ **\<** ](section-element.md) sectionName является пользовательским элементом, определяемым разделом > тегом в [ **\<элементе > configSections**](configsections-element-for-configuration.md) .  **\<** Система конфигурации возвращает <xref:System.Collections.IDictionary> объект при вызове метода <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем примере объявляется пользовательский элемент с именем  **\<самплесектион >** , который содержит <xref:System.Configuration.SingleTagSectionHandler> параметры, считанные классом:

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

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
