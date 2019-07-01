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
ms.openlocfilehash: b9a43c5f5141e364ab9aac1cfdff577a8fb8a161
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486683"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="a51fe-102">\<System.Web > элемент (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="a51fe-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="a51fe-103">Содержит сведения об управлении поведению процессов, используемые уровнем размещения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a51fe-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="a51fe-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a51fe-104">\<configuration></span></span>  
<span data-ttu-id="a51fe-105">\<System.Web > элемент (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="a51fe-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a51fe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a51fe-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a51fe-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a51fe-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a51fe-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a51fe-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a51fe-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a51fe-109">Attributes</span></span>  
 <span data-ttu-id="a51fe-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a51fe-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a51fe-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a51fe-111">Child Elements</span></span>  
  
|<span data-ttu-id="a51fe-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a51fe-112">Element</span></span>|<span data-ttu-id="a51fe-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a51fe-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a51fe-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="a51fe-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="a51fe-115">Задает параметры конфигурации для пулов приложений IIS в файле aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="a51fe-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a51fe-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a51fe-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a51fe-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="a51fe-117">Element</span></span>|<span data-ttu-id="a51fe-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a51fe-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a51fe-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a51fe-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="a51fe-120">Указывает корневой элемент в любом файле конфигурации, который используется среда CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a51fe-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a51fe-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a51fe-121">Remarks</span></span>  
 <span data-ttu-id="a51fe-122">`system.web` Элемента и его дочерних `applicationPool` элемента были добавлены в .NET Framework, начиная с .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="a51fe-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="a51fe-123">При работе в режиме интеграции с IIS 7.0 или более поздних версий это сочетание элементов позволяет настроить, как ASP.NET управляет потоками и как помещает запросы в очередь, когда ASP.NET размещен в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="a51fe-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="a51fe-124">При запуске IIS 7.0 или более поздних версий в классическом режиме или режиме ISAPI эти параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="a51fe-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a51fe-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a51fe-125">Example</span></span>  
 <span data-ttu-id="a51fe-126">В следующем примере показано, как настроить поведение всего процесса ASP.NET в файле aspnet.config, когда ASP.NET размещен в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="a51fe-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="a51fe-127">В примере предполагается, что службы IIS выполняются в интегрированном режиме, и что приложение использует .NET Framework 3.5 SP1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a51fe-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="a51fe-128">Это происходит в версиях .NET Framework более ранней, чем .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="a51fe-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="a51fe-129">В примере значения являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a51fe-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="a51fe-130">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="a51fe-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a51fe-131">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="a51fe-131">Namespace</span></span>||  
|<span data-ttu-id="a51fe-132">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="a51fe-132">Schema Name</span></span>||  
|<span data-ttu-id="a51fe-133">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="a51fe-133">Validation File</span></span>||  
|<span data-ttu-id="a51fe-134">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="a51fe-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a51fe-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a51fe-135">See also</span></span>

- [<span data-ttu-id="a51fe-136">Элемент \<applicationPool> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="a51fe-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
