---
title: Элемент <system.web> (веб-параметры)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152845"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="eba17-102">\<system.web> элемент (веб-настройки)</span><span class="sxs-lookup"><span data-stu-id="eba17-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="eba17-103">Содержит информацию о том, как ASP.NET слой хостинга управляет поведением в масштабах всего процесса.</span><span class="sxs-lookup"><span data-stu-id="eba17-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="eba17-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="eba17-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="eba17-105">&nbsp;&nbsp;**\<system.web>**</span><span class="sxs-lookup"><span data-stu-id="eba17-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba17-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eba17-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eba17-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eba17-107">Attributes and Elements</span></span>  

<span data-ttu-id="eba17-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eba17-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eba17-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eba17-109">Attributes</span></span>  

<span data-ttu-id="eba17-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="eba17-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eba17-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eba17-111">Child Elements</span></span>  
  
|<span data-ttu-id="eba17-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="eba17-112">Element</span></span>|<span data-ttu-id="eba17-113">Описание</span><span class="sxs-lookup"><span data-stu-id="eba17-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eba17-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="eba17-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="eba17-115">Определяет настройки конфигурации для пулов приложений IIS в файле aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="eba17-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eba17-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eba17-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eba17-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="eba17-117">Element</span></span>|<span data-ttu-id="eba17-118">Описание</span><span class="sxs-lookup"><span data-stu-id="eba17-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eba17-119">\<конфигурация></span><span class="sxs-lookup"><span data-stu-id="eba17-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="eba17-120">Определяет корневой элемент в каждом файле конфигурации, который используется приложениями общего языка и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eba17-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eba17-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="eba17-121">Remarks</span></span>  

<span data-ttu-id="eba17-122">Элемент `system.web` и его `applicationPool` элемент ребенка были добавлены в рамку .NET по состоянию на .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="eba17-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="eba17-123">При запуске IIS 7.0 или более поздних версий в интегрированном режиме эта комбинация элементов позволяет настроить, как ASP.NET управляет потоками и как он выстраивает в очередь запросы при размещении ASP.NET в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="eba17-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="eba17-124">Если вы запустите IIS 7.0 или более поздние версии в режиме Classic или ISAPI, эти параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="eba17-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eba17-125">Пример</span><span class="sxs-lookup"><span data-stu-id="eba17-125">Example</span></span>  

<span data-ttu-id="eba17-126">В следующем примере показано, как настроить поведение ASP.NET процесса в файле aspnet.config, когда ASP.NET размещается в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="eba17-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="eba17-127">Пример предполагает, что IIS работает в интегрированном режиме и что приложение использует .NET Framework 3.5 SP1 или более позднюю версию.</span><span class="sxs-lookup"><span data-stu-id="eba17-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="eba17-128">Такое поведение не происходит в версиях рамочного соглашения .NET раньше, чем .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="eba17-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="eba17-129">Значения в примере являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eba17-129">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="eba17-130">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="eba17-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eba17-131">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="eba17-131">Namespace</span></span>||  
|<span data-ttu-id="eba17-132">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="eba17-132">Schema Name</span></span>||  
|<span data-ttu-id="eba17-133">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="eba17-133">Validation File</span></span>||  
|<span data-ttu-id="eba17-134">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="eba17-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="eba17-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eba17-135">See also</span></span>

- [<span data-ttu-id="eba17-136">\<applicationPool> элемент (веб-настройки)</span><span class="sxs-lookup"><span data-stu-id="eba17-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
