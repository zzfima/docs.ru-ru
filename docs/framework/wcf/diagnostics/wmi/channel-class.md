---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 108d5f8e3cd092863dbd48e2bb9d180798b091a4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197877"
---
# <a name="channel-class"></a><span data-ttu-id="bdac0-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="bdac0-102">Channel class</span></span>
<span data-ttu-id="bdac0-103">Канал</span><span class="sxs-lookup"><span data-stu-id="bdac0-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdac0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdac0-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bdac0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bdac0-105">Methods</span></span>  
 <span data-ttu-id="bdac0-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="bdac0-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bdac0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="bdac0-107">Properties</span></span>  
 <span data-ttu-id="bdac0-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="bdac0-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="bdac0-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="bdac0-109">LocalAddress</span></span>  
 <span data-ttu-id="bdac0-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bdac0-110">Data type: string</span></span>  
  
 <span data-ttu-id="bdac0-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bdac0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdac0-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="bdac0-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="bdac0-113">ref</span><span class="sxs-lookup"><span data-stu-id="bdac0-113">ref</span></span>  
 <span data-ttu-id="bdac0-114">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="bdac0-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="bdac0-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bdac0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdac0-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="bdac0-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="bdac0-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="bdac0-117">RemoteAddress</span></span>  
 <span data-ttu-id="bdac0-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bdac0-118">Data type: string</span></span>  
  
 <span data-ttu-id="bdac0-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bdac0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdac0-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="bdac0-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="bdac0-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="bdac0-121">SessionId</span></span>  
 <span data-ttu-id="bdac0-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bdac0-122">Data type: string</span></span>  
  
 <span data-ttu-id="bdac0-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bdac0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdac0-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="bdac0-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="bdac0-125">Тип</span><span class="sxs-lookup"><span data-stu-id="bdac0-125">Type</span></span>  
 <span data-ttu-id="bdac0-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bdac0-126">Data type: string</span></span>  
  
 <span data-ttu-id="bdac0-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bdac0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdac0-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="bdac0-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdac0-129">Требования</span><span class="sxs-lookup"><span data-stu-id="bdac0-129">Requirements</span></span>  
  
|<span data-ttu-id="bdac0-130">MOF</span><span class="sxs-lookup"><span data-stu-id="bdac0-130">MOF</span></span>|<span data-ttu-id="bdac0-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bdac0-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bdac0-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="bdac0-132">Namespace</span></span>|<span data-ttu-id="bdac0-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bdac0-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdac0-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bdac0-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
