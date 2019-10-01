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
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699141"
---
# <a name="web-settings-schema"></a><span data-ttu-id="521fb-102">Схема веб-параметров</span><span class="sxs-lookup"><span data-stu-id="521fb-102">Web Settings Schema</span></span>
<span data-ttu-id="521fb-103">Веб-параметры определяют настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="521fb-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="521fb-104">Эти параметры отличаются от параметров типа домена приложения, которые задаются в файле Web.config приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="521fb-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="521fb-105">Веб-параметры содержатся в файлах Aspnet.config, которые находятся в папках установки версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="521fb-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="521fb-106">Например, файл ASPNET. config для .NET Framework 2,0 находится в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="521fb-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="521fb-107">Веб-параметры не используются в других файлах конфигурации, таких как файл machine.config, корневой файл Web.config или файлы Web.config уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="521fb-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="521fb-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="521fb-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="521fb-109">&nbsp; @ no__t-1[ **@no__t -4system. Web >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="521fb-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="521fb-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<applicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="521fb-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="521fb-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="521fb-111">Element</span></span>|<span data-ttu-id="521fb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="521fb-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="521fb-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="521fb-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="521fb-114">Содержит сведения, используемые уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="521fb-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="521fb-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="521fb-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="521fb-116">Определяет настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="521fb-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="521fb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="521fb-117">See also</span></span>

- [<span data-ttu-id="521fb-118">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="521fb-118">Configuration File Schema</span></span>](../index.md)
