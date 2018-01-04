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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3995b517b27a5565f7fcb9c11da27c9e1bb40887
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="f461d-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f461d-102">ChannelPoolSettings</span></span>
<span data-ttu-id="f461d-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f461d-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f461d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f461d-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f461d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f461d-105">Methods</span></span>  
 <span data-ttu-id="f461d-106">Класс ChannelPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f461d-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f461d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f461d-107">Properties</span></span>  
 <span data-ttu-id="f461d-108">Класс ChannelPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f461d-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="f461d-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f461d-109">IdleTimeout</span></span>  
 <span data-ttu-id="f461d-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f461d-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="f461d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f461d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f461d-112">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="f461d-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="f461d-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="f461d-113">LeaseTimeout</span></span>  
 <span data-ttu-id="f461d-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f461d-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="f461d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f461d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f461d-116">Максимальное время ожидания завершения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="f461d-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="f461d-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f461d-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="f461d-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f461d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f461d-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f461d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f461d-120">Максимальное число исходящих каналов для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f461d-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f461d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="f461d-121">Requirements</span></span>  
  
|<span data-ttu-id="f461d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f461d-122">MOF</span></span>|<span data-ttu-id="f461d-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f461d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f461d-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f461d-124">Namespace</span></span>|<span data-ttu-id="f461d-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f461d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f461d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f461d-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
