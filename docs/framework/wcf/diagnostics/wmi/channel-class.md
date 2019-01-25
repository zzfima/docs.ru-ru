---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668396"
---
# <a name="channel-class"></a><span data-ttu-id="76626-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="76626-102">Channel class</span></span>
<span data-ttu-id="76626-103">Канал</span><span class="sxs-lookup"><span data-stu-id="76626-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76626-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76626-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="76626-105">Методы</span><span class="sxs-lookup"><span data-stu-id="76626-105">Methods</span></span>  
 <span data-ttu-id="76626-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="76626-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="76626-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="76626-107">Properties</span></span>  
 <span data-ttu-id="76626-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="76626-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="76626-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="76626-109">LocalAddress</span></span>  
 <span data-ttu-id="76626-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="76626-110">Data type: string</span></span>  
  
 <span data-ttu-id="76626-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="76626-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="76626-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="76626-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="76626-113">ref</span><span class="sxs-lookup"><span data-stu-id="76626-113">ref</span></span>  
 <span data-ttu-id="76626-114">Тип данных: Конечная точка</span><span class="sxs-lookup"><span data-stu-id="76626-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="76626-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="76626-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="76626-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="76626-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="76626-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="76626-117">RemoteAddress</span></span>  
 <span data-ttu-id="76626-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="76626-118">Data type: string</span></span>  
  
 <span data-ttu-id="76626-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="76626-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="76626-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="76626-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="76626-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="76626-121">SessionId</span></span>  
 <span data-ttu-id="76626-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="76626-122">Data type: string</span></span>  
  
 <span data-ttu-id="76626-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="76626-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="76626-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="76626-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="76626-125">Тип</span><span class="sxs-lookup"><span data-stu-id="76626-125">Type</span></span>  
 <span data-ttu-id="76626-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="76626-126">Data type: string</span></span>  
  
 <span data-ttu-id="76626-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="76626-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="76626-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="76626-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76626-129">Требования</span><span class="sxs-lookup"><span data-stu-id="76626-129">Requirements</span></span>  
  
|<span data-ttu-id="76626-130">MOF</span><span class="sxs-lookup"><span data-stu-id="76626-130">MOF</span></span>|<span data-ttu-id="76626-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="76626-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="76626-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="76626-132">Namespace</span></span>|<span data-ttu-id="76626-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="76626-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76626-134">См. также</span><span class="sxs-lookup"><span data-stu-id="76626-134">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelBase>
