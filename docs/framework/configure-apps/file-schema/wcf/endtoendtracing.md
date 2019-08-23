---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b23728451a051f21ad3863b9a29e6290c3c837a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919015"
---
# <a name="endtoendtracing"></a><span data-ttu-id="08475-101">\<ЕндтоендтраЦинг ></span><span class="sxs-lookup"><span data-stu-id="08475-101">\<endToEndTracing></span></span>
<span data-ttu-id="08475-102">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="08475-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="08475-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08475-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="08475-104">\<Диагностические ></span><span class="sxs-lookup"><span data-stu-id="08475-104">\<diagnostic></span></span>  
<span data-ttu-id="08475-105">\<ЕндтоендтраЦинг ></span><span class="sxs-lookup"><span data-stu-id="08475-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08475-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08475-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08475-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08475-107">Attributes and Elements</span></span>  
 <span data-ttu-id="08475-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08475-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08475-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08475-109">Attributes</span></span>  
  
|<span data-ttu-id="08475-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08475-110">Attribute</span></span>|<span data-ttu-id="08475-111">Описание</span><span class="sxs-lookup"><span data-stu-id="08475-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="08475-112">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="08475-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="08475-113">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="08475-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="08475-114">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="08475-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08475-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08475-115">Child Elements</span></span>  
 <span data-ttu-id="08475-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="08475-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08475-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08475-117">Parent Elements</span></span>  
  
|<span data-ttu-id="08475-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="08475-118">Element</span></span>|<span data-ttu-id="08475-119">Описание</span><span class="sxs-lookup"><span data-stu-id="08475-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08475-120">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="08475-120">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="08475-121">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="08475-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08475-122">См. также</span><span class="sxs-lookup"><span data-stu-id="08475-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="08475-123">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="08475-123">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
