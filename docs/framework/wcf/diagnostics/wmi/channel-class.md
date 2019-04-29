---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964091"
---
# <a name="channel-class"></a><span data-ttu-id="09373-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="09373-102">Channel class</span></span>
<span data-ttu-id="09373-103">Канал</span><span class="sxs-lookup"><span data-stu-id="09373-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09373-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09373-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="09373-105">Методы</span><span class="sxs-lookup"><span data-stu-id="09373-105">Methods</span></span>  
 <span data-ttu-id="09373-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="09373-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="09373-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="09373-107">Properties</span></span>  
 <span data-ttu-id="09373-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="09373-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="09373-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="09373-109">LocalAddress</span></span>  
 <span data-ttu-id="09373-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="09373-110">Data type: string</span></span>  
  
 <span data-ttu-id="09373-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="09373-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09373-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="09373-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="09373-113">ref</span><span class="sxs-lookup"><span data-stu-id="09373-113">ref</span></span>  
 <span data-ttu-id="09373-114">Тип данных: Конечная точка</span><span class="sxs-lookup"><span data-stu-id="09373-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="09373-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="09373-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09373-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="09373-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="09373-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="09373-117">RemoteAddress</span></span>  
 <span data-ttu-id="09373-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="09373-118">Data type: string</span></span>  
  
 <span data-ttu-id="09373-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="09373-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09373-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="09373-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="09373-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="09373-121">SessionId</span></span>  
 <span data-ttu-id="09373-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="09373-122">Data type: string</span></span>  
  
 <span data-ttu-id="09373-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="09373-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09373-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="09373-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="09373-125">Тип</span><span class="sxs-lookup"><span data-stu-id="09373-125">Type</span></span>  
 <span data-ttu-id="09373-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="09373-126">Data type: string</span></span>  
  
 <span data-ttu-id="09373-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="09373-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09373-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="09373-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09373-129">Требования</span><span class="sxs-lookup"><span data-stu-id="09373-129">Requirements</span></span>  
  
|<span data-ttu-id="09373-130">MOF</span><span class="sxs-lookup"><span data-stu-id="09373-130">MOF</span></span>|<span data-ttu-id="09373-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="09373-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="09373-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="09373-132">Namespace</span></span>|<span data-ttu-id="09373-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="09373-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09373-134">См. также</span><span class="sxs-lookup"><span data-stu-id="09373-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
