---
title: '&lt;endToEndTracing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb187302000291fd6b540b562ed7aebf1db7add2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="af2da-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="af2da-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="af2da-103">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="af2da-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="af2da-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="af2da-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="af2da-105">\<диагностические ></span><span class="sxs-lookup"><span data-stu-id="af2da-105">\<diagnostic></span></span>  
<span data-ttu-id="af2da-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="af2da-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af2da-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af2da-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af2da-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="af2da-108">Attributes and Elements</span></span>  
 <span data-ttu-id="af2da-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="af2da-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af2da-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="af2da-110">Attributes</span></span>  
  
|<span data-ttu-id="af2da-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="af2da-111">Attribute</span></span>|<span data-ttu-id="af2da-112">Описание</span><span class="sxs-lookup"><span data-stu-id="af2da-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="af2da-113">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="af2da-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="af2da-114">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="af2da-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="af2da-115">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="af2da-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af2da-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="af2da-116">Child Elements</span></span>  
 <span data-ttu-id="af2da-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="af2da-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af2da-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="af2da-118">Parent Elements</span></span>  
  
|<span data-ttu-id="af2da-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="af2da-119">Element</span></span>|<span data-ttu-id="af2da-120">Описание</span><span class="sxs-lookup"><span data-stu-id="af2da-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af2da-121">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="af2da-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="af2da-122">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="af2da-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af2da-123">См. также</span><span class="sxs-lookup"><span data-stu-id="af2da-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="af2da-124">End-to-End трассировки</span><span class="sxs-lookup"><span data-stu-id="af2da-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
