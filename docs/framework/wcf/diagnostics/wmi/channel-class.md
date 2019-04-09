---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128847"
---
# <a name="channel-class"></a><span data-ttu-id="0490e-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="0490e-102">Channel class</span></span>
<span data-ttu-id="0490e-103">Канал</span><span class="sxs-lookup"><span data-stu-id="0490e-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0490e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0490e-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0490e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0490e-105">Methods</span></span>  
 <span data-ttu-id="0490e-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="0490e-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0490e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="0490e-107">Properties</span></span>  
 <span data-ttu-id="0490e-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0490e-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="0490e-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="0490e-109">LocalAddress</span></span>  
 <span data-ttu-id="0490e-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0490e-110">Data type: string</span></span>  
  
 <span data-ttu-id="0490e-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0490e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0490e-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="0490e-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0490e-113">ref</span><span class="sxs-lookup"><span data-stu-id="0490e-113">ref</span></span>  
 <span data-ttu-id="0490e-114">Тип данных: Конечная точка</span><span class="sxs-lookup"><span data-stu-id="0490e-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="0490e-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0490e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0490e-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="0490e-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="0490e-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="0490e-117">RemoteAddress</span></span>  
 <span data-ttu-id="0490e-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0490e-118">Data type: string</span></span>  
  
 <span data-ttu-id="0490e-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0490e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0490e-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="0490e-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="0490e-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="0490e-121">SessionId</span></span>  
 <span data-ttu-id="0490e-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0490e-122">Data type: string</span></span>  
  
 <span data-ttu-id="0490e-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0490e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0490e-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="0490e-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="0490e-125">Тип</span><span class="sxs-lookup"><span data-stu-id="0490e-125">Type</span></span>  
 <span data-ttu-id="0490e-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0490e-126">Data type: string</span></span>  
  
 <span data-ttu-id="0490e-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0490e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0490e-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="0490e-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0490e-129">Требования</span><span class="sxs-lookup"><span data-stu-id="0490e-129">Requirements</span></span>  
  
|<span data-ttu-id="0490e-130">MOF</span><span class="sxs-lookup"><span data-stu-id="0490e-130">MOF</span></span>|<span data-ttu-id="0490e-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0490e-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0490e-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0490e-132">Namespace</span></span>|<span data-ttu-id="0490e-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0490e-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0490e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0490e-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
