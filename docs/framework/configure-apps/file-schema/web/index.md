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
ms.openlocfilehash: 030841330ff37cddb0c9e3e466a55a4be098e784
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088791"
---
# <a name="web-settings-schema"></a><span data-ttu-id="1a684-102">Схема веб-параметров</span><span class="sxs-lookup"><span data-stu-id="1a684-102">Web Settings Schema</span></span>
<span data-ttu-id="1a684-103">Веб-параметры определяют настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1a684-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="1a684-104">Эти параметры отличаются от параметров типа домена приложения, которые задаются в файле Web.config приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1a684-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="1a684-105">Веб-параметры содержатся в файлах Aspnet.config, которые находятся в папках установки версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a684-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="1a684-106">Например, файл ASPNET. config для .NET Framework 2,0 находится в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="1a684-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="1a684-107">Веб-параметры не используются в других файлах конфигурации, таких как файл machine.config, корневой файл Web.config или файлы Web.config уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="1a684-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  

<span data-ttu-id="1a684-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a684-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a684-109">&nbsp;&nbsp;[ **\<System. web >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1a684-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>\
<span data-ttu-id="1a684-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ApplicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1a684-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>

|<span data-ttu-id="1a684-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="1a684-111">Element</span></span>|<span data-ttu-id="1a684-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1a684-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a684-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="1a684-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="1a684-114">Содержит сведения, используемые уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1a684-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="1a684-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="1a684-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="1a684-116">Определяет настройки ЦП и настройки ASP.NET на уровне выполнения, которые относятся к поведению процессов, управляемых уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1a684-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a684-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1a684-117">See also</span></span>

- [<span data-ttu-id="1a684-118">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1a684-118">Configuration File Schema</span></span>](../index.md)
