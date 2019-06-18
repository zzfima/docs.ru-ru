---
title: Схема веб-параметров
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 0fbc28bb7b871cc245d0fe477ea8e15c147549bb
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170022"
---
# <a name="web-settings-schema"></a>Схема веб-параметров
Веб-параметры определяют настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET. Эти параметры отличаются от параметров типа домена приложения, которые задаются в файле Web.config приложения ASP.NET.  
  
 Веб-параметры содержатся в файлах Aspnet.config, которые находятся в папках установки версий .NET Framework. Например файл Aspnet.config для .NET Framework 2.0 находится в следующей папке:  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 Веб-параметры не используются в других файлах конфигурации, таких как файл machine.config, корневой файл Web.config или файлы Web.config уровня приложения.  
  
 [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [Элемент \<system.web> (веб-параметры)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [Элемент \<applicationPool> (веб-параметры)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Содержит сведения, используемые уровнем размещения ASP.NET.|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Определяет настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.|  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
