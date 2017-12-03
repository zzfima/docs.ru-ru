---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abaacfb6541d41019a8d0cd6df53913c6b7911f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="51031-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="51031-102">OneWayBindingElement</span></span>
<span data-ttu-id="51031-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="51031-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51031-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51031-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="51031-105">Методы</span><span class="sxs-lookup"><span data-stu-id="51031-105">Methods</span></span>  
 <span data-ttu-id="51031-106">Класс OneWayBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="51031-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="51031-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="51031-107">Properties</span></span>  
 <span data-ttu-id="51031-108">Класс OneWayBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="51031-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="51031-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="51031-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="51031-110">Тип данных: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="51031-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="51031-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="51031-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="51031-112">Параметры пула каналов.</span><span class="sxs-lookup"><span data-stu-id="51031-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="51031-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="51031-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="51031-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="51031-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="51031-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="51031-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="51031-116">Максимальное число принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="51031-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="51031-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="51031-117">PacketRoutable</span></span>  
 <span data-ttu-id="51031-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="51031-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="51031-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="51031-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="51031-120">Значение, указывающее, возможна ли маршрутизация пакета.</span><span class="sxs-lookup"><span data-stu-id="51031-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51031-121">Требования</span><span class="sxs-lookup"><span data-stu-id="51031-121">Requirements</span></span>  
  
|<span data-ttu-id="51031-122">MOF</span><span class="sxs-lookup"><span data-stu-id="51031-122">MOF</span></span>|<span data-ttu-id="51031-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="51031-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="51031-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="51031-124">Namespace</span></span>|<span data-ttu-id="51031-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="51031-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51031-126">См. также</span><span class="sxs-lookup"><span data-stu-id="51031-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
