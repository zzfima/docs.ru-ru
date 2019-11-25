---
title: Элемент <add> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865c693bf8f23bf050064ac097b72aa6fa3b371e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088747"
---
# <a name="add-element-for-appsettings"></a>\<добавить элемент > для \<appSettings >

Добавляет пользовательский параметр приложения.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a>Атрибуты

|           | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Указывает имя добавляемого ключа. |
| **value** | Обязательный атрибут.<br><br>Указывает значение добавляемого ключа. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения. |

## <a name="child-elements"></a>Дочерние элементы

Отсутствуют

## <a name="example"></a>Пример

В следующем примере показано, как добавить настраиваемый параметр конфигурации для имени приложения:

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

В следующем примере элемент `<add>` используется для определения двух параметров совместимости в приложении ASP.NET:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](../index.md)
