---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925842"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="bfa3b-101">\<Диспатчерсинчронизатион ></span><span class="sxs-lookup"><span data-stu-id="bfa3b-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="bfa3b-102">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="bfa3b-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="bfa3b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="bfa3b-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="bfa3b-104">\<behaviors></span></span>  
<span data-ttu-id="bfa3b-105">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bfa3b-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="bfa3b-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="bfa3b-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa3b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfa3b-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="bfa3b-108">Тип</span><span class="sxs-lookup"><span data-stu-id="bfa3b-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfa3b-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="bfa3b-109">Attributes and elements</span></span>  
  
<span data-ttu-id="bfa3b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfa3b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bfa3b-111">Attributes</span></span>

| <span data-ttu-id="bfa3b-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bfa3b-112">Attribute</span></span>               | <span data-ttu-id="bfa3b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bfa3b-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="bfa3b-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="bfa3b-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="bfa3b-115">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="bfa3b-116">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="bfa3b-117">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="bfa3b-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bfa3b-118">Child elements</span></span>

<span data-ttu-id="bfa3b-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bfa3b-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bfa3b-120">Parent elements</span></span>

| <span data-ttu-id="bfa3b-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="bfa3b-121">Element</span></span> | <span data-ttu-id="bfa3b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="bfa3b-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="bfa3b-123">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="bfa3b-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="bfa3b-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bfa3b-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="bfa3b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bfa3b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
