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
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a><span data-ttu-id="20a24-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="20a24-102">Channel class</span></span>
<span data-ttu-id="20a24-103">Канал</span><span class="sxs-lookup"><span data-stu-id="20a24-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20a24-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="20a24-105">Методы</span><span class="sxs-lookup"><span data-stu-id="20a24-105">Methods</span></span>  
 <span data-ttu-id="20a24-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="20a24-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="20a24-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="20a24-107">Properties</span></span>  
 <span data-ttu-id="20a24-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="20a24-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="20a24-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="20a24-109">LocalAddress</span></span>  
 <span data-ttu-id="20a24-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="20a24-110">Data type: string</span></span>  
  
 <span data-ttu-id="20a24-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="20a24-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20a24-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="20a24-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="20a24-113">ref</span><span class="sxs-lookup"><span data-stu-id="20a24-113">ref</span></span>  
 <span data-ttu-id="20a24-114">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="20a24-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="20a24-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="20a24-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20a24-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="20a24-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="20a24-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="20a24-117">RemoteAddress</span></span>  
 <span data-ttu-id="20a24-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="20a24-118">Data type: string</span></span>  
  
 <span data-ttu-id="20a24-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="20a24-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20a24-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="20a24-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="20a24-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="20a24-121">SessionId</span></span>  
 <span data-ttu-id="20a24-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="20a24-122">Data type: string</span></span>  
  
 <span data-ttu-id="20a24-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="20a24-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20a24-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="20a24-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="20a24-125">Тип</span><span class="sxs-lookup"><span data-stu-id="20a24-125">Type</span></span>  
 <span data-ttu-id="20a24-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="20a24-126">Data type: string</span></span>  
  
 <span data-ttu-id="20a24-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="20a24-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20a24-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="20a24-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20a24-129">Требования</span><span class="sxs-lookup"><span data-stu-id="20a24-129">Requirements</span></span>  
  
|<span data-ttu-id="20a24-130">MOF</span><span class="sxs-lookup"><span data-stu-id="20a24-130">MOF</span></span>|<span data-ttu-id="20a24-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="20a24-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="20a24-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="20a24-132">Namespace</span></span>|<span data-ttu-id="20a24-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="20a24-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20a24-134">См. также</span><span class="sxs-lookup"><span data-stu-id="20a24-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
