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
ms.openlocfilehash: 5c5c857d4494b6d78b819e56bae4213abc5e2035
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699094"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="729b2-102">Элемент \<System. Web > (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="729b2-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="729b2-103">Содержит сведения о том, как уровень размещения ASP.NET управляет поведением всего процесса.</span><span class="sxs-lookup"><span data-stu-id="729b2-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="729b2-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="729b2-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="729b2-105">&nbsp;&nbsp; **\<System. web >**</span><span class="sxs-lookup"><span data-stu-id="729b2-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="729b2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="729b2-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="729b2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="729b2-107">Attributes and Elements</span></span>  

<span data-ttu-id="729b2-108">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="729b2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="729b2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="729b2-109">Attributes</span></span>  

<span data-ttu-id="729b2-110">Нет</span><span class="sxs-lookup"><span data-stu-id="729b2-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="729b2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="729b2-111">Child Elements</span></span>  
  
|<span data-ttu-id="729b2-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="729b2-112">Element</span></span>|<span data-ttu-id="729b2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="729b2-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="729b2-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="729b2-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="729b2-115">Задает параметры конфигурации для пулов приложений IIS в файле aspnet. config.</span><span class="sxs-lookup"><span data-stu-id="729b2-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="729b2-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="729b2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="729b2-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="729b2-117">Element</span></span>|<span data-ttu-id="729b2-118">Описание</span><span class="sxs-lookup"><span data-stu-id="729b2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="729b2-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="729b2-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="729b2-120">Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.</span><span class="sxs-lookup"><span data-stu-id="729b2-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="729b2-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="729b2-121">Remarks</span></span>  

<span data-ttu-id="729b2-122">Элемент `system.web` и его дочерний элемент `applicationPool` были добавлены в .NET Framework в .NET Framework 3,5 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="729b2-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="729b2-123">При запуске IIS 7,0 или более поздних версий в интегрированном режиме эта комбинация элементов позволяет настроить, как ASP.NET управляет потоками и как она помещает запросы в очередь, когда ASP.NET размещается в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="729b2-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="729b2-124">При запуске IIS 7,0 или более поздних версий в классическом или режиме ISAPI эти параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="729b2-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="729b2-125">Пример</span><span class="sxs-lookup"><span data-stu-id="729b2-125">Example</span></span>  

<span data-ttu-id="729b2-126">В следующем примере показано, как настроить поведение ASP.NET на уровне процесса в файле aspnet. config, если ASP.NET размещается в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="729b2-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="729b2-127">В примере предполагается, что службы IIS работают в режиме интеграции и что приложение использует .NET Framework 3,5 с пакетом обновления 1 (SP1) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="729b2-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="729b2-128">Такое поведение не происходит в версиях .NET Framework более ранних, чем .NET Framework 3,5 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="729b2-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="729b2-129">Значения в примере являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="729b2-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="729b2-130">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="729b2-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="729b2-131">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="729b2-131">Namespace</span></span>||  
|<span data-ttu-id="729b2-132">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="729b2-132">Schema Name</span></span>||  
|<span data-ttu-id="729b2-133">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="729b2-133">Validation File</span></span>||  
|<span data-ttu-id="729b2-134">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="729b2-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="729b2-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="729b2-135">See also</span></span>

- [<span data-ttu-id="729b2-136">Элемент \<applicationPool> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="729b2-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
