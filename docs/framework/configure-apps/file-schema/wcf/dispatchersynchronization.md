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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 24ae6dbf0fb67b5755aca848ea7fce6abda14b0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="b8d06-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="b8d06-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="b8d06-103">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="b8d06-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="b8d06-104">\<system.serviceModel > \<поведения > \<endpointBehaviors > \<поведения ></span><span class="sxs-lookup"><span data-stu-id="b8d06-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="b8d06-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8d06-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="b8d06-106">Тип</span><span class="sxs-lookup"><span data-stu-id="b8d06-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="b8d06-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="b8d06-107">Attributes and elements</span></span>

<span data-ttu-id="b8d06-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b8d06-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b8d06-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b8d06-109">Attributes</span></span>

| <span data-ttu-id="b8d06-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b8d06-110">Attribute</span></span>               | <span data-ttu-id="b8d06-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d06-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="b8d06-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="b8d06-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="b8d06-113">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="b8d06-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="b8d06-114">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="b8d06-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="b8d06-115">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="b8d06-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="b8d06-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b8d06-116">Child elements</span></span>

<span data-ttu-id="b8d06-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b8d06-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b8d06-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b8d06-118">Parent elements</span></span>

| <span data-ttu-id="b8d06-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b8d06-119">Element</span></span> | <span data-ttu-id="b8d06-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d06-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="b8d06-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="b8d06-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b8d06-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b8d06-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b8d06-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b8d06-123">See also</span></span>

 <span data-ttu-id="b8d06-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="b8d06-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
