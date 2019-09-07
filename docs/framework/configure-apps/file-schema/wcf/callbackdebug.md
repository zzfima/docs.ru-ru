---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400568"
---
# <a name="callbackdebug"></a><span data-ttu-id="b440a-101">\<Каллбаккдебуг ></span><span class="sxs-lookup"><span data-stu-id="b440a-101">\<callbackDebug></span></span>
<span data-ttu-id="b440a-102">Указывает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b440a-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="b440a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b440a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b440a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b440a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b440a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b440a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b440a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b440a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b440a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b440a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b440a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Каллбаккдебуг >**</span><span class="sxs-lookup"><span data-stu-id="b440a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b440a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b440a-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="b440a-110">Тип</span><span class="sxs-lookup"><span data-stu-id="b440a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b440a-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b440a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b440a-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b440a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b440a-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b440a-113">Attributes</span></span>  
  
|<span data-ttu-id="b440a-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b440a-114">Attribute</span></span>|<span data-ttu-id="b440a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b440a-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="b440a-116">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="b440a-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="b440a-117">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="b440a-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="b440a-118">**Внимание!**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b440a-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="b440a-119">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="b440a-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b440a-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b440a-120">Child Elements</span></span>  
 <span data-ttu-id="b440a-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="b440a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b440a-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b440a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b440a-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b440a-123">Element</span></span>|<span data-ttu-id="b440a-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b440a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b440a-125">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b440a-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b440a-126">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b440a-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b440a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b440a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
