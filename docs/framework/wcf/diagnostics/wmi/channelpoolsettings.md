---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a56616e97526b2d410d18d97dc1391c6fc32cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="156a7-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="156a7-102">ChannelPoolSettings</span></span>
<span data-ttu-id="156a7-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="156a7-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="156a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="156a7-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="156a7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="156a7-105">Methods</span></span>  
 <span data-ttu-id="156a7-106">Класс ChannelPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="156a7-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="156a7-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="156a7-107">Properties</span></span>  
 <span data-ttu-id="156a7-108">Класс ChannelPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="156a7-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="156a7-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="156a7-109">IdleTimeout</span></span>  
 <span data-ttu-id="156a7-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="156a7-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="156a7-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="156a7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="156a7-112">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="156a7-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="156a7-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="156a7-113">LeaseTimeout</span></span>  
 <span data-ttu-id="156a7-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="156a7-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="156a7-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="156a7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="156a7-116">Максимальное время ожидания завершения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="156a7-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="156a7-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="156a7-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="156a7-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="156a7-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="156a7-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="156a7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="156a7-120">Максимальное число исходящих каналов для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="156a7-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="156a7-121">Требования</span><span class="sxs-lookup"><span data-stu-id="156a7-121">Requirements</span></span>  
  
|<span data-ttu-id="156a7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="156a7-122">MOF</span></span>|<span data-ttu-id="156a7-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="156a7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="156a7-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="156a7-124">Namespace</span></span>|<span data-ttu-id="156a7-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="156a7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="156a7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="156a7-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
