---
title: Элемент <remove> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0fcdb75aa733a9d7634ec1c3b31dcbbb87e090e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088718"
---
# <a name="remove-element-for-appsettings"></a>\<удалить элемент > для \<appSettings >

Удаляет пользовательские параметры приложения.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>Атрибут

|         | Описание |
| ------- | ----------- |
| **key** | Обязательный атрибут.<br><br>Задает имя удаляемого ключа. |

### <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения. |

## <a name="child-elements"></a>Дочерние элементы

Отсутствуют

## <a name="example"></a>Пример

В следующем примере показано, как удалить настраиваемый параметр конфигурации для `ApplicationName`.

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](../index.md)
