---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099291"
---
# <a name="persistenceprovider"></a><span data-ttu-id="42f06-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="42f06-101">\<persistenceProvider></span></span>
<span data-ttu-id="42f06-102">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="42f06-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="42f06-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="42f06-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="42f06-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="42f06-104">\<behaviors></span></span>  
<span data-ttu-id="42f06-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="42f06-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="42f06-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="42f06-106">\<behavior></span></span>  
<span data-ttu-id="42f06-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="42f06-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f06-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42f06-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42f06-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42f06-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42f06-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="42f06-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42f06-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42f06-111">Attributes</span></span>  
  
|<span data-ttu-id="42f06-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="42f06-112">Attribute</span></span>|<span data-ttu-id="42f06-113">Описание</span><span class="sxs-lookup"><span data-stu-id="42f06-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42f06-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="42f06-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="42f06-115">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="42f06-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="42f06-116">Значение по умолчанию — «00: 00:30».</span><span class="sxs-lookup"><span data-stu-id="42f06-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="42f06-117">type</span><span class="sxs-lookup"><span data-stu-id="42f06-117">type</span></span>|<span data-ttu-id="42f06-118">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="42f06-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42f06-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42f06-119">Child Elements</span></span>  
 <span data-ttu-id="42f06-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="42f06-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42f06-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42f06-121">Parent Elements</span></span>  
  
|<span data-ttu-id="42f06-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="42f06-122">Element</span></span>|<span data-ttu-id="42f06-123">Описание</span><span class="sxs-lookup"><span data-stu-id="42f06-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42f06-124">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="42f06-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="42f06-125">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="42f06-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42f06-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="42f06-126">Remarks</span></span>  
 <span data-ttu-id="42f06-127">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="42f06-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="42f06-128">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="42f06-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f06-129">См. также</span><span class="sxs-lookup"><span data-stu-id="42f06-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
