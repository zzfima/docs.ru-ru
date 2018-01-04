---
title: "Класс Channel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 073f0a2a2731a08acd914a7dd85cb2b419d98128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="channel-class"></a><span data-ttu-id="bcdeb-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="bcdeb-102">Channel class</span></span>
<span data-ttu-id="bcdeb-103">Канал</span><span class="sxs-lookup"><span data-stu-id="bcdeb-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcdeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcdeb-104">Syntax</span></span>  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bcdeb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bcdeb-105">Methods</span></span>  
 <span data-ttu-id="bcdeb-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bcdeb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="bcdeb-107">Properties</span></span>  
 <span data-ttu-id="bcdeb-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="bcdeb-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="bcdeb-109">LocalAddress</span></span>  
 <span data-ttu-id="bcdeb-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bcdeb-110">Data type: string</span></span>  
  
 <span data-ttu-id="bcdeb-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bcdeb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcdeb-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="bcdeb-113">ref</span><span class="sxs-lookup"><span data-stu-id="bcdeb-113">ref</span></span>  
 <span data-ttu-id="bcdeb-114">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="bcdeb-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="bcdeb-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bcdeb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcdeb-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="bcdeb-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="bcdeb-117">RemoteAddress</span></span>  
 <span data-ttu-id="bcdeb-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bcdeb-118">Data type: string</span></span>  
  
 <span data-ttu-id="bcdeb-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bcdeb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcdeb-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="bcdeb-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="bcdeb-121">SessionId</span></span>  
 <span data-ttu-id="bcdeb-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bcdeb-122">Data type: string</span></span>  
  
 <span data-ttu-id="bcdeb-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bcdeb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcdeb-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="bcdeb-125">Тип</span><span class="sxs-lookup"><span data-stu-id="bcdeb-125">Type</span></span>  
 <span data-ttu-id="bcdeb-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bcdeb-126">Data type: string</span></span>  
  
 <span data-ttu-id="bcdeb-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bcdeb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcdeb-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcdeb-129">Требования</span><span class="sxs-lookup"><span data-stu-id="bcdeb-129">Requirements</span></span>  
  
|<span data-ttu-id="bcdeb-130">MOF</span><span class="sxs-lookup"><span data-stu-id="bcdeb-130">MOF</span></span>|<span data-ttu-id="bcdeb-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bcdeb-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="bcdeb-132">Namespace</span></span>|<span data-ttu-id="bcdeb-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bcdeb-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcdeb-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bcdeb-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
