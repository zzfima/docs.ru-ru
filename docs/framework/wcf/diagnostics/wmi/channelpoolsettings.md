---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: d763be92243768bce9fdaefcd3e3575effac464b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200487"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="e0c0a-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e0c0a-102">ChannelPoolSettings</span></span>
<span data-ttu-id="e0c0a-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e0c0a-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0c0a-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e0c0a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e0c0a-105">Methods</span></span>  
 <span data-ttu-id="e0c0a-106">Класс ChannelPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e0c0a-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e0c0a-107">Properties</span></span>  
 <span data-ttu-id="e0c0a-108">Класс ChannelPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="e0c0a-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="e0c0a-109">IdleTimeout</span></span>  
 <span data-ttu-id="e0c0a-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="e0c0a-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="e0c0a-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e0c0a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0c0a-112">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="e0c0a-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="e0c0a-113">LeaseTimeout</span></span>  
 <span data-ttu-id="e0c0a-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="e0c0a-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e0c0a-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e0c0a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0c0a-116">Максимальное время ожидания завершения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="e0c0a-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e0c0a-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="e0c0a-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="e0c0a-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="e0c0a-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e0c0a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0c0a-120">Максимальное число исходящих каналов для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c0a-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e0c0a-121">Requirements</span></span>  
  
|<span data-ttu-id="e0c0a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e0c0a-122">MOF</span></span>|<span data-ttu-id="e0c0a-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e0c0a-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e0c0a-124">Namespace</span></span>|<span data-ttu-id="e0c0a-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e0c0a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0c0a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e0c0a-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
