---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 266b33e9b0386d0346a86ba8bd82cc65def4f0c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180158"
---
# <a name="endtoendtracing"></a><span data-ttu-id="b3224-101">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="b3224-101">\<endToEndTracing></span></span>
<span data-ttu-id="b3224-102">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="b3224-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="b3224-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b3224-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3224-104">\<диагностические ></span><span class="sxs-lookup"><span data-stu-id="b3224-104">\<diagnostic></span></span>  
<span data-ttu-id="b3224-105">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="b3224-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3224-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3224-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3224-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b3224-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b3224-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3224-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3224-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3224-109">Attributes</span></span>  
  
|<span data-ttu-id="b3224-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3224-110">Attribute</span></span>|<span data-ttu-id="b3224-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b3224-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="b3224-112">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="b3224-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="b3224-113">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="b3224-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="b3224-114">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="b3224-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3224-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3224-115">Child Elements</span></span>  
 <span data-ttu-id="b3224-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b3224-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3224-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3224-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b3224-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3224-118">Element</span></span>|<span data-ttu-id="b3224-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b3224-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3224-120">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="b3224-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="b3224-121">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="b3224-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3224-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b3224-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="b3224-123">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="b3224-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
