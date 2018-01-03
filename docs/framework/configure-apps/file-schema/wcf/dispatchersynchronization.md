---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57477ea60337e5032b80bd9ae8da850099dd08f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="0f1f1-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="0f1f1-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="0f1f1-103">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="0f1f1-104">\<system.serviceModel > \<поведения > \<endpointBehaviors > \<поведения ></span><span class="sxs-lookup"><span data-stu-id="0f1f1-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="0f1f1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f1f1-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="0f1f1-106">Тип</span><span class="sxs-lookup"><span data-stu-id="0f1f1-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="0f1f1-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f1f1-107">Attributes and elements</span></span>

<span data-ttu-id="0f1f1-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f1f1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f1f1-109">Attributes</span></span>

| <span data-ttu-id="0f1f1-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0f1f1-110">Attribute</span></span>               | <span data-ttu-id="0f1f1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="0f1f1-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="0f1f1-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="0f1f1-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="0f1f1-113">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="0f1f1-114">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="0f1f1-115">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="0f1f1-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f1f1-116">Child elements</span></span>

<span data-ttu-id="0f1f1-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f1f1-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f1f1-118">Parent elements</span></span>

| <span data-ttu-id="0f1f1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f1f1-119">Element</span></span> | <span data-ttu-id="0f1f1-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="0f1f1-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="0f1f1-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0f1f1-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0f1f1-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0f1f1-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0f1f1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0f1f1-123">See also</span></span>

 <span data-ttu-id="0f1f1-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="0f1f1-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
