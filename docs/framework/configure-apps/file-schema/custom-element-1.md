---
title: Пользовательский элемент для SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635398"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Пользовательский элемент для SingleTagSectionHandler

Определяет настройки в специальном разделе конфигурации, который определяется разделом \<> элементом и использует <xref:System.Configuration.SingleTagSectionHandler> класс.

конфигурация &nbsp; &nbsp; [** \<>**](configuration-element.md) * \<разделаName>*

## <a name="syntax"></a>Синтаксис

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>Атрибуты

Атрибуты и значения атрибутов определяются пользователем.

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<конфигурация>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

Отсутствуют

## <a name="remarks"></a>Примечания

** \<Элемент sectionName>** является пользовательским элементом, определяемым [** \<разделом>**](section-element.md) тегом [** \<в элементе configSections>.**](configsections-element-for-configuration.md) Система конфигурации <xref:System.Collections.IDictionary> возвращает объект <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>при вызове.

## <a name="example"></a>Пример

В следующем примере объявляется пользовательский элемент, называемый <xref:System.Configuration.SingleTagSectionHandler> ** \<sampleSection>,** содержащий параметры, прочитаны классом:

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

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема конфигурации файла для рамочного соглашения .NET](index.md)
