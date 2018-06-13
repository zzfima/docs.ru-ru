---
title: '&lt;System.Web&gt; элемент (веб-параметров)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7527ee9e7528a0da47529bae93e8112705e03a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755166"
---
# <a name="ltsystemwebgt-element-web-settings"></a><span data-ttu-id="8af7e-102">&lt;System.Web&gt; элемент (веб-параметров)</span><span class="sxs-lookup"><span data-stu-id="8af7e-102">&lt;system.web&gt; Element (Web Settings)</span></span>
<span data-ttu-id="8af7e-103">Содержит сведения о том, как уровень размещения ASP.NET управляет поведением на уровне процесса.</span><span class="sxs-lookup"><span data-stu-id="8af7e-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="8af7e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8af7e-104">\<configuration></span></span>  
<span data-ttu-id="8af7e-105">\<System.Web > элемент (веб-параметров)</span><span class="sxs-lookup"><span data-stu-id="8af7e-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af7e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8af7e-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8af7e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8af7e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8af7e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8af7e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8af7e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8af7e-109">Attributes</span></span>  
 <span data-ttu-id="8af7e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8af7e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8af7e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8af7e-111">Child Elements</span></span>  
  
|<span data-ttu-id="8af7e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8af7e-112">Element</span></span>|<span data-ttu-id="8af7e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8af7e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8af7e-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="8af7e-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="8af7e-115">Задает параметры конфигурации для пулов приложений IIS в файле aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="8af7e-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8af7e-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8af7e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8af7e-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="8af7e-117">Element</span></span>|<span data-ttu-id="8af7e-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8af7e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8af7e-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8af7e-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="8af7e-120">Указывает корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8af7e-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af7e-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="8af7e-121">Remarks</span></span>  
 <span data-ttu-id="8af7e-122">`system.web` Элемента и его дочерних `applicationPool` добавлен элемент [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] в [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af7e-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="8af7e-123">При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в интегрированном режиме это сочетание элементов позволяет настроить, как ASP.NET управляет потоками и как помещает запросы в очередь, когда ASP.NET размещен в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="8af7e-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="8af7e-124">При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в классическом режиме или режиме ISAPI, эти параметры учитываются.</span><span class="sxs-lookup"><span data-stu-id="8af7e-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8af7e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="8af7e-125">Example</span></span>  
 <span data-ttu-id="8af7e-126">В следующем примере показано, как настроить поведение всего процесса ASP.NET в файле aspnet.config, когда ASP.NET размещен в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="8af7e-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="8af7e-127">В примере предполагается, что службы IIS запущены в интегрированном режиме, а приложение использует [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8af7e-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="8af7e-128">Этого не происходит в версиях [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] более раннюю, чем [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af7e-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="8af7e-129">В примере используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8af7e-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="8af7e-130">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="8af7e-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8af7e-131">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8af7e-131">Namespace</span></span>||  
|<span data-ttu-id="8af7e-132">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="8af7e-132">Schema Name</span></span>||  
|<span data-ttu-id="8af7e-133">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="8af7e-133">Validation File</span></span>||  
|<span data-ttu-id="8af7e-134">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="8af7e-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="8af7e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8af7e-135">See Also</span></span>  
 [<span data-ttu-id="8af7e-136">Элемент \<applicationPool> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="8af7e-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
