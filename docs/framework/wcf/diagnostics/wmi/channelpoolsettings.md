---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 48b41d2f3f45cd9c590f87151253450962b994de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="channelpoolsettings"></a><span data-ttu-id="49766-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="49766-102">ChannelPoolSettings</span></span>
<span data-ttu-id="49766-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="49766-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49766-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49766-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="49766-105">Методы</span><span class="sxs-lookup"><span data-stu-id="49766-105">Methods</span></span>  
 <span data-ttu-id="49766-106">Класс ChannelPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="49766-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="49766-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="49766-107">Properties</span></span>  
 <span data-ttu-id="49766-108">Класс ChannelPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="49766-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="49766-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="49766-109">IdleTimeout</span></span>  
 <span data-ttu-id="49766-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="49766-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="49766-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49766-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49766-112">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="49766-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="49766-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="49766-113">LeaseTimeout</span></span>  
 <span data-ttu-id="49766-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="49766-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="49766-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49766-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49766-116">Максимальное время ожидания завершения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="49766-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="49766-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="49766-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="49766-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="49766-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="49766-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49766-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49766-120">Максимальное число исходящих каналов для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="49766-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49766-121">Требования</span><span class="sxs-lookup"><span data-stu-id="49766-121">Requirements</span></span>  
  
|<span data-ttu-id="49766-122">MOF</span><span class="sxs-lookup"><span data-stu-id="49766-122">MOF</span></span>|<span data-ttu-id="49766-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="49766-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="49766-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="49766-124">Namespace</span></span>|<span data-ttu-id="49766-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="49766-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49766-126">См. также</span><span class="sxs-lookup"><span data-stu-id="49766-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
