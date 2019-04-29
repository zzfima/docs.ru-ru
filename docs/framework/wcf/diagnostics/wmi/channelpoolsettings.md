---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 8900af77d0d385bb68b4b85e1d15be57bb7a8d14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963984"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="240eb-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="240eb-102">ChannelPoolSettings</span></span>
<span data-ttu-id="240eb-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="240eb-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="240eb-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="240eb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="240eb-105">Methods</span></span>  
 <span data-ttu-id="240eb-106">Класс ChannelPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="240eb-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="240eb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="240eb-107">Properties</span></span>  
 <span data-ttu-id="240eb-108">Класс ChannelPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="240eb-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="240eb-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="240eb-109">IdleTimeout</span></span>  
 <span data-ttu-id="240eb-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="240eb-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="240eb-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="240eb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="240eb-112">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="240eb-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="240eb-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="240eb-113">LeaseTimeout</span></span>  
 <span data-ttu-id="240eb-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="240eb-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="240eb-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="240eb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="240eb-116">Максимальное время ожидания завершения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="240eb-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="240eb-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="240eb-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="240eb-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="240eb-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="240eb-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="240eb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="240eb-120">Максимальное число исходящих каналов для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="240eb-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="240eb-121">Требования</span><span class="sxs-lookup"><span data-stu-id="240eb-121">Requirements</span></span>  
  
|<span data-ttu-id="240eb-122">MOF</span><span class="sxs-lookup"><span data-stu-id="240eb-122">MOF</span></span>|<span data-ttu-id="240eb-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="240eb-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="240eb-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="240eb-124">Namespace</span></span>|<span data-ttu-id="240eb-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="240eb-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="240eb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="240eb-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
