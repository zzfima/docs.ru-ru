---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398005"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="3d783-101">\<Диспатчерсинчронизатион ></span><span class="sxs-lookup"><span data-stu-id="3d783-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="3d783-102">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="3d783-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="3d783-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3d783-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3d783-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3d783-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3d783-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3d783-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3d783-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3d783-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="3d783-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3d783-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="3d783-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Диспатчерсинчронизатион >**</span><span class="sxs-lookup"><span data-stu-id="3d783-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d783-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d783-109">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="3d783-110">Тип</span><span class="sxs-lookup"><span data-stu-id="3d783-110">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d783-111">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d783-111">Attributes and elements</span></span>  
  
<span data-ttu-id="3d783-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d783-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d783-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d783-113">Attributes</span></span>

| <span data-ttu-id="3d783-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3d783-114">Attribute</span></span>               | <span data-ttu-id="3d783-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3d783-115">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="3d783-116">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="3d783-116">asynchronousSendEnabled</span></span> | <span data-ttu-id="3d783-117">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="3d783-117">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="3d783-118">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="3d783-118">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="3d783-119">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="3d783-119">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3d783-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d783-120">Child elements</span></span>

<span data-ttu-id="3d783-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="3d783-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3d783-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d783-122">Parent elements</span></span>

| <span data-ttu-id="3d783-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d783-123">Element</span></span> | <span data-ttu-id="3d783-124">Описание</span><span class="sxs-lookup"><span data-stu-id="3d783-124">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="3d783-125">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3d783-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3d783-126">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3d783-126">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3d783-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3d783-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
