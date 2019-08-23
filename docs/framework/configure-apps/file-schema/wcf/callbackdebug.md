---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 91e7bd63bf496f2c38776d88173ed2ac12a3b888
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926307"
---
# <a name="callbackdebug"></a><span data-ttu-id="3bdb8-101">\<Каллбаккдебуг ></span><span class="sxs-lookup"><span data-stu-id="3bdb8-101">\<callbackDebug></span></span>
<span data-ttu-id="3bdb8-102">Указывает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3bdb8-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="3bdb8-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3bdb8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3bdb8-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3bdb8-104">\<behaviors></span></span>  
<span data-ttu-id="3bdb8-105">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3bdb8-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="3bdb8-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3bdb8-106">\<behavior></span></span>  
<span data-ttu-id="3bdb8-107">\<Каллбаккдебуг ></span><span class="sxs-lookup"><span data-stu-id="3bdb8-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bdb8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bdb8-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="3bdb8-109">Тип</span><span class="sxs-lookup"><span data-stu-id="3bdb8-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bdb8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3bdb8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3bdb8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bdb8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3bdb8-112">Attributes</span></span>  
  
|<span data-ttu-id="3bdb8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3bdb8-113">Attribute</span></span>|<span data-ttu-id="3bdb8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3bdb8-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="3bdb8-115">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="3bdb8-116">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="3bdb8-117">**Внимание!**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="3bdb8-118">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bdb8-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3bdb8-119">Child Elements</span></span>  
 <span data-ttu-id="3bdb8-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3bdb8-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3bdb8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3bdb8-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="3bdb8-122">Element</span></span>|<span data-ttu-id="3bdb8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="3bdb8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bdb8-124">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3bdb8-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3bdb8-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bdb8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3bdb8-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
