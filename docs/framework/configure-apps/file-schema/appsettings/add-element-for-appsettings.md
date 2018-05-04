---
title: '&lt;Добавить&gt; элемент для &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 35a9fc08033d2b9cd1dae5a1f1f3ddcd361f03eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="add-element-for-appsettings"></a>\<Добавить > элемент для \<appSettings >

Добавляет пользовательский параметр приложения.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Добавить >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a>Атрибуты

|           | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Задает имя ключа. |
| **value** | Обязательный атрибут.<br><br>Указывает значение ключа. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="example"></a>Пример

Следующий пример демонстрирует добавление настроек пользовательской конфигурации для имени приложения:

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a>См. также

[Схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
