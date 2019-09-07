---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400068"
---
# <a name="persistenceprovider"></a><span data-ttu-id="7798f-101">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="7798f-101">\<persistenceProvider></span></span>
<span data-ttu-id="7798f-102">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="7798f-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
<span data-ttu-id="7798f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7798f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7798f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7798f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7798f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7798f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistenceProvider >**</span><span class="sxs-lookup"><span data-stu-id="7798f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7798f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7798f-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7798f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7798f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7798f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7798f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7798f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7798f-112">Attributes</span></span>  
  
|<span data-ttu-id="7798f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7798f-113">Attribute</span></span>|<span data-ttu-id="7798f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7798f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7798f-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="7798f-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="7798f-116">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="7798f-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="7798f-117">Значение по умолчанию — "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="7798f-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="7798f-118">type</span><span class="sxs-lookup"><span data-stu-id="7798f-118">type</span></span>|<span data-ttu-id="7798f-119">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="7798f-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7798f-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7798f-120">Child Elements</span></span>  
 <span data-ttu-id="7798f-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="7798f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7798f-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7798f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7798f-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="7798f-123">Element</span></span>|<span data-ttu-id="7798f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="7798f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7798f-125">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="7798f-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7798f-126">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="7798f-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7798f-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7798f-127">Remarks</span></span>  
 <span data-ttu-id="7798f-128">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="7798f-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="7798f-129">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="7798f-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7798f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="7798f-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
