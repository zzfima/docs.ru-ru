---
title: Элемент <add> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 594ba4f289012e775e93acba98056b60bdd94cbd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927752"
---
# <a name="add-element-for-appsettings"></a>\<Добавьте элемент > для \<appSettings >

Добавляет пользовательский параметр приложения.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**

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

В следующем примере `<add>` элемент используется для определения двух параметров совместимости в приложении ASP.NET:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](../index.md)
