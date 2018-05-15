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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 93d0d2ea5cf3b0329d9b1a03a233cff2d8133072
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="web-settings-schema"></a><span data-ttu-id="5ec53-102">Схема веб-параметров</span><span class="sxs-lookup"><span data-stu-id="5ec53-102">Web Settings Schema</span></span>
<span data-ttu-id="5ec53-103">Веб-параметры определяют настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5ec53-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="5ec53-104">Эти параметры отличаются от параметров типа домена приложения, которые задаются в файле Web.config приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5ec53-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="5ec53-105">Веб-параметры содержатся в файлах Aspnet.config, которые находятся в папках установки версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ec53-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="5ec53-106">Например, файл Aspnet.config для [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] находится в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="5ec53-106">For example, the Aspnet.config file for [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="5ec53-107">Веб-параметры не используются в других файлах конфигурации, таких как файл machine.config, корневой файл Web.config или файлы Web.config уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="5ec53-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="5ec53-108">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="5ec53-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="5ec53-109">Элемент \<system.web> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="5ec53-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="5ec53-110">Элемент \<applicationPool> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="5ec53-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="5ec53-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ec53-111">Element</span></span>|<span data-ttu-id="5ec53-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5ec53-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ec53-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="5ec53-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="5ec53-114">Содержит сведения, используемые уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5ec53-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="5ec53-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="5ec53-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="5ec53-116">Определяет настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5ec53-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ec53-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5ec53-117">See Also</span></span>  
 [<span data-ttu-id="5ec53-118">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="5ec53-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
