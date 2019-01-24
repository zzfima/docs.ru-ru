---
title: '&lt;endToEndTracing&gt;'
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: c2f5e33eff4fdc6dfa85bcc10b59a7c1436cabb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519403"
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="d9f83-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="d9f83-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="d9f83-103">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d9f83-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="d9f83-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9f83-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9f83-105">\<диагностические ></span><span class="sxs-lookup"><span data-stu-id="d9f83-105">\<diagnostic></span></span>  
<span data-ttu-id="d9f83-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="d9f83-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f83-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9f83-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9f83-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d9f83-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9f83-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d9f83-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9f83-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d9f83-110">Attributes</span></span>  
  
|<span data-ttu-id="d9f83-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d9f83-111">Attribute</span></span>|<span data-ttu-id="d9f83-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d9f83-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="d9f83-113">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="d9f83-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="d9f83-114">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="d9f83-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="d9f83-115">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="d9f83-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9f83-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d9f83-116">Child Elements</span></span>  
 <span data-ttu-id="d9f83-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d9f83-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9f83-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d9f83-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d9f83-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9f83-119">Element</span></span>|<span data-ttu-id="d9f83-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="d9f83-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9f83-121">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="d9f83-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="d9f83-122">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="d9f83-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9f83-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d9f83-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="d9f83-124">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="d9f83-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
