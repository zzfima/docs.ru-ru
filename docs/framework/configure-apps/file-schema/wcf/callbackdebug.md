---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704522"
---
# <a name="callbackdebug"></a><span data-ttu-id="a45df-101">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="a45df-101">\<callbackDebug></span></span>
<span data-ttu-id="a45df-102">Задает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a45df-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="a45df-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a45df-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a45df-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="a45df-104">\<behaviors></span></span>  
<span data-ttu-id="a45df-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a45df-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="a45df-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a45df-106">\<behavior></span></span>  
<span data-ttu-id="a45df-107">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="a45df-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45df-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a45df-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="a45df-109">Тип</span><span class="sxs-lookup"><span data-stu-id="a45df-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a45df-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a45df-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a45df-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a45df-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a45df-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a45df-112">Attributes</span></span>  
  
|<span data-ttu-id="a45df-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a45df-113">Attribute</span></span>|<span data-ttu-id="a45df-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a45df-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="a45df-115">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="a45df-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="a45df-116">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="a45df-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="a45df-117">**Внимание!**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a45df-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="a45df-118">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="a45df-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a45df-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a45df-119">Child Elements</span></span>  
 <span data-ttu-id="a45df-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a45df-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a45df-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a45df-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a45df-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="a45df-122">Element</span></span>|<span data-ttu-id="a45df-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a45df-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a45df-124">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a45df-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a45df-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a45df-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a45df-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a45df-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
