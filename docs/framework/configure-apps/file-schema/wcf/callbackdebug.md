---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 1aa292a3fe06af9cf1dbc53ebf5bbdf9841be8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687379"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="a8344-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="a8344-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="a8344-103">Задает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a8344-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="a8344-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a8344-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a8344-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="a8344-105">\<behaviors></span></span>  
<span data-ttu-id="a8344-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a8344-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a8344-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a8344-107">\<behavior></span></span>  
<span data-ttu-id="a8344-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="a8344-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8344-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8344-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="a8344-110">Тип</span><span class="sxs-lookup"><span data-stu-id="a8344-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8344-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8344-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a8344-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8344-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8344-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8344-113">Attributes</span></span>  
  
|<span data-ttu-id="a8344-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a8344-114">Attribute</span></span>|<span data-ttu-id="a8344-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a8344-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="a8344-116">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="a8344-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="a8344-117">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="a8344-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="a8344-118">**Внимание!**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a8344-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="a8344-119">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="a8344-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8344-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8344-120">Child Elements</span></span>  
 <span data-ttu-id="a8344-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a8344-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8344-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8344-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a8344-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8344-123">Element</span></span>|<span data-ttu-id="a8344-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="a8344-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8344-125">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a8344-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a8344-126">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a8344-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8344-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a8344-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
