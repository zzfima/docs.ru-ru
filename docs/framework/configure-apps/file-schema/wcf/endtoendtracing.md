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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1bcd7405c5e3ebf2d1c156ff3bca9f473df9fa35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="aa98d-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="aa98d-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="aa98d-103">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="aa98d-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="aa98d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aa98d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa98d-105">\<диагностические ></span><span class="sxs-lookup"><span data-stu-id="aa98d-105">\<diagnostic></span></span>  
<span data-ttu-id="aa98d-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="aa98d-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa98d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa98d-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa98d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa98d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aa98d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa98d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa98d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa98d-110">Attributes</span></span>  
  
|<span data-ttu-id="aa98d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aa98d-111">Attribute</span></span>|<span data-ttu-id="aa98d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aa98d-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="aa98d-113">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="aa98d-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="aa98d-114">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="aa98d-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="aa98d-115">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="aa98d-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa98d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa98d-116">Child Elements</span></span>  
 <span data-ttu-id="aa98d-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aa98d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa98d-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa98d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aa98d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa98d-119">Element</span></span>|<span data-ttu-id="aa98d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="aa98d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa98d-121">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="aa98d-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="aa98d-122">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="aa98d-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa98d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="aa98d-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="aa98d-124">End-to-End трассировки</span><span class="sxs-lookup"><span data-stu-id="aa98d-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
