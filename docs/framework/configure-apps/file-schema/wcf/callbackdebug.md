---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 5bd2356c3bb798e948341cb3c4ba504ac886ed44
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145085"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="f3185-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="f3185-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="f3185-103">Задает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f3185-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="f3185-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f3185-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3185-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="f3185-105">\<behaviors></span></span>  
<span data-ttu-id="f3185-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f3185-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f3185-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="f3185-107">\<behavior></span></span>  
<span data-ttu-id="f3185-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="f3185-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3185-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3185-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="f3185-110">Тип</span><span class="sxs-lookup"><span data-stu-id="f3185-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3185-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3185-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f3185-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3185-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3185-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3185-113">Attributes</span></span>  
  
|<span data-ttu-id="f3185-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3185-114">Attribute</span></span>|<span data-ttu-id="f3185-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f3185-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="f3185-116">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="f3185-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="f3185-117">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="f3185-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="f3185-118">**Внимание!**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f3185-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="f3185-119">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="f3185-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3185-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3185-120">Child Elements</span></span>  
 <span data-ttu-id="f3185-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f3185-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3185-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3185-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f3185-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3185-123">Element</span></span>|<span data-ttu-id="f3185-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="f3185-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3185-125">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="f3185-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f3185-126">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f3185-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3185-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f3185-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
