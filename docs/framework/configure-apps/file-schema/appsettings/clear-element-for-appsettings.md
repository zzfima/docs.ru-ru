---
title: Элемент <clear> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921312"
---
# <a name="clear-element-for-appsettings"></a>\<Очистка элемента > для \<appSettings >

Удаляет пользовательские параметры приложения.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Атрибуты

Отсутствуют

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML или другие сведения о конфигурации пользовательских приложений. |

## <a name="child-elements"></a>Дочерние элементы

Отсутствуют

## <a name="example"></a>Пример

В следующем примере показано, как удалить настраиваемые параметры конфигурации.

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](../index.md)
