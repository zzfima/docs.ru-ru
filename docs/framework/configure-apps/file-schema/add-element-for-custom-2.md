---
title: '&lt;Добавить&gt; элемент NameValueSectionHandler и DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: aeb3e3a4be201369ca2df8d231498dd2400d3c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Добавить > элемент NameValueSectionHandler и DictionarySectionHandler

Добавляет пользовательские параметры приложения. Каждый  **\<Добавить >** тег содержит пару ключ значение.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Добавить >**

## <a name="syntax"></a>Синтаксис

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Атрибуты

| Атрибут | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Указывает имя параметра. |
| **value** | Обязательный атрибут.<br><br>Задает значение параметра. |

## <a name="parent-element"></a>Родительский элемент

| Элемент | Описание |
| ------- | ------------|
| [**\<sectionName >** элемент](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="example"></a>Пример

В следующем примере показано определение настраиваемого раздела конфигурации и использование  **\<Добавить >** элемент для задания параметров в разделе:

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.

## <a name="see-also"></a>См. также

[Схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
