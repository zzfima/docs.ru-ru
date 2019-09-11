---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855298"
---
# <a name="endtoendtracing"></a><span data-ttu-id="0432c-101">\<ЕндтоендтраЦинг ></span><span class="sxs-lookup"><span data-stu-id="0432c-101">\<endToEndTracing></span></span>
<span data-ttu-id="0432c-102">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="0432c-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
<span data-ttu-id="0432c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0432c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0432c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0432c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0432c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Диагностика >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="0432c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="0432c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ЕндтоендтраЦинг >**</span><span class="sxs-lookup"><span data-stu-id="0432c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0432c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0432c-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0432c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0432c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0432c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0432c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0432c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0432c-110">Attributes</span></span>  
  
|<span data-ttu-id="0432c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0432c-111">Attribute</span></span>|<span data-ttu-id="0432c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0432c-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="0432c-113">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="0432c-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="0432c-114">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="0432c-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="0432c-115">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="0432c-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0432c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0432c-116">Child Elements</span></span>  
 <span data-ttu-id="0432c-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="0432c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0432c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0432c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0432c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0432c-119">Element</span></span>|<span data-ttu-id="0432c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0432c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0432c-121">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="0432c-121">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="0432c-122">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="0432c-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0432c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0432c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="0432c-124">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="0432c-124">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
