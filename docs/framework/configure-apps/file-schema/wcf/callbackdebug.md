---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152273"
---
# <a name="callbackdebug"></a><span data-ttu-id="21a45-101">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="21a45-101">\<callbackDebug></span></span>
<span data-ttu-id="21a45-102">Задает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="21a45-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="21a45-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="21a45-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="21a45-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="21a45-104">\<behaviors></span></span>  
<span data-ttu-id="21a45-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="21a45-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="21a45-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="21a45-106">\<behavior></span></span>  
<span data-ttu-id="21a45-107">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="21a45-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a45-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21a45-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="21a45-109">Тип</span><span class="sxs-lookup"><span data-stu-id="21a45-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21a45-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="21a45-110">Attributes and Elements</span></span>  
 <span data-ttu-id="21a45-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="21a45-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21a45-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21a45-112">Attributes</span></span>  
  
|<span data-ttu-id="21a45-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="21a45-113">Attribute</span></span>|<span data-ttu-id="21a45-114">Описание</span><span class="sxs-lookup"><span data-stu-id="21a45-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="21a45-115">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="21a45-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="21a45-116">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="21a45-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="21a45-117">**Внимание!**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="21a45-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="21a45-118">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="21a45-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21a45-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21a45-119">Child Elements</span></span>  
 <span data-ttu-id="21a45-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="21a45-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21a45-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21a45-121">Parent Elements</span></span>  
  
|<span data-ttu-id="21a45-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="21a45-122">Element</span></span>|<span data-ttu-id="21a45-123">Описание</span><span class="sxs-lookup"><span data-stu-id="21a45-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21a45-124">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="21a45-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="21a45-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="21a45-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21a45-126">См. также</span><span class="sxs-lookup"><span data-stu-id="21a45-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
