---
title: Настраиваемый элемент для SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: ad98617cd4e88d1650f67136536b7dd5994233a4
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301157"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Настраиваемый элемент для SingleTagSectionHandler

Определяет параметры настраиваемого раздела конфигурации, определяемый \<разделе > элемент и использует <xref:System.Configuration.SingleTagSectionHandler> класса.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp; *\<параметра sectionName >*

## <a name="syntax"></a>Синтаксис

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Атрибуты

Атрибуты и значения атрибутов являются определяемые пользователем.

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Примечания

 **\<Параметра sectionName >** элемент является пользовательским элементом определяется [  **\<разделе >** ](~/docs/framework/configure-apps/file-schema/section-element.md) тегом [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) элемент. Система конфигурации возвращает <xref:System.Collections.IDictionary> объекта при вызове <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем примере объявляется пользовательский элемент с именем  **\<sampleSection >** , содержащий параметры, считываемые <xref:System.Configuration.SingleTagSectionHandler> класса:

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

Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
