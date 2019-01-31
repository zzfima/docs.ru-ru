---
title: <remove> элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: c86d231a4e3e8e15df94017a6ca461b365643ea5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267421"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Удалить > элемент для NameValueSectionHandler и DictionarySectionHandler

Удаляет ранее определенный параметр.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<параметра sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалить >**

## <a name="syntax"></a>Синтаксис

```xml
<add remove="key" />
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Указывает имя параметра для удаления. |

## <a name="parent-element"></a>Родительский элемент

| Элемент | Описание: |
| ------- | ------------|
| [**\<параметра sectionName >** элемент](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="remarks"></a>Примечания

Можно использовать  **\<удалить >** элемент для удаления параметров из приложения, которые были определены на более высоком уровне в иерархии файла конфигурации.

## <a name="example"></a>Пример

В следующем примере показано, как использовать  **\<удалить >** элемент в файле конфигурации приложения для удаления параметров, определенных ранее в файле конфигурации компьютера.

В коде следующего файла конфигурации компьютера объявляет разделе  **\<mySection >** и добавляет два параметра `key1` и `key2`, к нему:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

В коде следующего файла конфигурации приложения удаляет `key2` Azure с помощью  **\<mySection >**:

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
