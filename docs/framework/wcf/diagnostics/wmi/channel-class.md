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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1df634a61cce695fca74fdfe53beea6c0f83d082
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="channel-class"></a><span data-ttu-id="0a9bf-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="0a9bf-102">Channel class</span></span>
<span data-ttu-id="0a9bf-103">Канал</span><span class="sxs-lookup"><span data-stu-id="0a9bf-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a9bf-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0a9bf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0a9bf-105">Methods</span></span>  
 <span data-ttu-id="0a9bf-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0a9bf-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="0a9bf-107">Properties</span></span>  
 <span data-ttu-id="0a9bf-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="0a9bf-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="0a9bf-109">LocalAddress</span></span>  
 <span data-ttu-id="0a9bf-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0a9bf-110">Data type: string</span></span>  
  
 <span data-ttu-id="0a9bf-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0a9bf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0a9bf-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0a9bf-113">ref</span><span class="sxs-lookup"><span data-stu-id="0a9bf-113">ref</span></span>  
 <span data-ttu-id="0a9bf-114">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a9bf-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="0a9bf-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0a9bf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0a9bf-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="0a9bf-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="0a9bf-117">RemoteAddress</span></span>  
 <span data-ttu-id="0a9bf-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0a9bf-118">Data type: string</span></span>  
  
 <span data-ttu-id="0a9bf-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0a9bf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0a9bf-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="0a9bf-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="0a9bf-121">SessionId</span></span>  
 <span data-ttu-id="0a9bf-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0a9bf-122">Data type: string</span></span>  
  
 <span data-ttu-id="0a9bf-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0a9bf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0a9bf-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="0a9bf-125">Тип</span><span class="sxs-lookup"><span data-stu-id="0a9bf-125">Type</span></span>  
 <span data-ttu-id="0a9bf-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0a9bf-126">Data type: string</span></span>  
  
 <span data-ttu-id="0a9bf-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0a9bf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0a9bf-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a9bf-129">Требования</span><span class="sxs-lookup"><span data-stu-id="0a9bf-129">Requirements</span></span>  
  
|<span data-ttu-id="0a9bf-130">MOF</span><span class="sxs-lookup"><span data-stu-id="0a9bf-130">MOF</span></span>|<span data-ttu-id="0a9bf-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0a9bf-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0a9bf-132">Namespace</span></span>|<span data-ttu-id="0a9bf-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0a9bf-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a9bf-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0a9bf-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
