---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555392"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="a59a0-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="a59a0-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="a59a0-103">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="a59a0-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="a59a0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a59a0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a59a0-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="a59a0-105">\<behaviors></span></span>  
<span data-ttu-id="a59a0-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a59a0-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a59a0-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a59a0-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59a0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a59a0-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="a59a0-109">Тип</span><span class="sxs-lookup"><span data-stu-id="a59a0-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a59a0-110">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a59a0-110">Attributes and elements</span></span>  
  
<span data-ttu-id="a59a0-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a59a0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a59a0-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a59a0-112">Attributes</span></span>

| <span data-ttu-id="a59a0-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a59a0-113">Attribute</span></span>               | <span data-ttu-id="a59a0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a59a0-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="a59a0-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="a59a0-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="a59a0-116">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="a59a0-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="a59a0-117">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="a59a0-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="a59a0-118">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="a59a0-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="a59a0-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a59a0-119">Child elements</span></span>

<span data-ttu-id="a59a0-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a59a0-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a59a0-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a59a0-121">Parent elements</span></span>

| <span data-ttu-id="a59a0-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="a59a0-122">Element</span></span> | <span data-ttu-id="a59a0-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="a59a0-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="a59a0-124">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a59a0-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a59a0-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a59a0-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a59a0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a59a0-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
