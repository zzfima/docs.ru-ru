---
title: <remove> - элемент для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: cf9a34e47b70aaff12b29b9c5cf944d5bb15fee9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258725"
---
# <a name="remove-element-for-appsettings"></a>\<Удалить > элемент для \<appSettings >

Удаляет пользовательские параметры приложения.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалить >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>Атрибут

|         | Описание: |
| ------- | ----------- |
| **key** | Обязательный атрибут.<br><br>Указывает имя ключа для удаления. |

### <a name="parent-element"></a>Родительский элемент

|     | Описание: |
| --- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="example"></a>Пример

В следующем примере показан способ удаления настроек пользовательской конфигурации для `ApplicationName`:

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
