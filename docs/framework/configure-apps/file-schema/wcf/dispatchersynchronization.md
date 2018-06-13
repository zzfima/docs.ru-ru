---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 34c12a05ee363df6b6cfc9ff3809bab50ee8d522
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747581"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="56236-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="56236-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="56236-103">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="56236-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="56236-104">\<system.serviceModel > \<поведения > \<endpointBehaviors > \<поведения ></span><span class="sxs-lookup"><span data-stu-id="56236-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="56236-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56236-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="56236-106">Тип</span><span class="sxs-lookup"><span data-stu-id="56236-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="56236-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="56236-107">Attributes and elements</span></span>

<span data-ttu-id="56236-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56236-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="56236-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56236-109">Attributes</span></span>

| <span data-ttu-id="56236-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="56236-110">Attribute</span></span>               | <span data-ttu-id="56236-111">Описание</span><span class="sxs-lookup"><span data-stu-id="56236-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="56236-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="56236-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="56236-113">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="56236-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="56236-114">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="56236-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="56236-115">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="56236-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="56236-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56236-116">Child elements</span></span>

<span data-ttu-id="56236-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="56236-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="56236-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56236-118">Parent elements</span></span>

| <span data-ttu-id="56236-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="56236-119">Element</span></span> | <span data-ttu-id="56236-120">Описание</span><span class="sxs-lookup"><span data-stu-id="56236-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="56236-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="56236-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="56236-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56236-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="56236-123">См. также</span><span class="sxs-lookup"><span data-stu-id="56236-123">See also</span></span>

 <span data-ttu-id="56236-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="56236-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
