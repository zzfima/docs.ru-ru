---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 6be9752e8102a5d4db4fed31aae8ff6d56fdd24e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273336"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="17fe5-101">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="17fe5-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="17fe5-102">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="17fe5-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="17fe5-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17fe5-103">\<system.serviceModel></span></span>  
<span data-ttu-id="17fe5-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="17fe5-104">\<behaviors></span></span>  
<span data-ttu-id="17fe5-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="17fe5-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="17fe5-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="17fe5-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17fe5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17fe5-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="17fe5-108">Тип</span><span class="sxs-lookup"><span data-stu-id="17fe5-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17fe5-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="17fe5-109">Attributes and elements</span></span>  
  
<span data-ttu-id="17fe5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17fe5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17fe5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="17fe5-111">Attributes</span></span>

| <span data-ttu-id="17fe5-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17fe5-112">Attribute</span></span>               | <span data-ttu-id="17fe5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="17fe5-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="17fe5-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="17fe5-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="17fe5-115">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="17fe5-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="17fe5-116">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="17fe5-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="17fe5-117">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="17fe5-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="17fe5-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="17fe5-118">Child elements</span></span>

<span data-ttu-id="17fe5-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="17fe5-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="17fe5-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="17fe5-120">Parent elements</span></span>

| <span data-ttu-id="17fe5-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="17fe5-121">Element</span></span> | <span data-ttu-id="17fe5-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="17fe5-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="17fe5-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="17fe5-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="17fe5-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="17fe5-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="17fe5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="17fe5-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
