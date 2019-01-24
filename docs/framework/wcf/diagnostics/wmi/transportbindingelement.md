---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 303e5523befb68c65bc50ee3933af58897929363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668461"
---
# <a name="transportbindingelement"></a><span data-ttu-id="928b2-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="928b2-102">TransportBindingElement</span></span>
<span data-ttu-id="928b2-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="928b2-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="928b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="928b2-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="928b2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="928b2-105">Methods</span></span>  
 <span data-ttu-id="928b2-106">Класс TransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="928b2-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="928b2-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="928b2-107">Properties</span></span>  
 <span data-ttu-id="928b2-108">Класс TransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="928b2-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="928b2-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="928b2-109">ManualAddressing</span></span>  
 <span data-ttu-id="928b2-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="928b2-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="928b2-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="928b2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="928b2-112">Логическое значение, указывающее, требуется ли пользователю контролировать адресацию сообщений.</span><span class="sxs-lookup"><span data-stu-id="928b2-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="928b2-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="928b2-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="928b2-114">Тип данных: sint64</span><span class="sxs-lookup"><span data-stu-id="928b2-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="928b2-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="928b2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="928b2-116">Максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="928b2-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="928b2-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="928b2-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="928b2-118">Тип данных: sint64</span><span class="sxs-lookup"><span data-stu-id="928b2-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="928b2-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="928b2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="928b2-120">Максимально размер сообщения, обрабатываемого данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="928b2-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="928b2-121">Схема</span><span class="sxs-lookup"><span data-stu-id="928b2-121">Scheme</span></span>  
 <span data-ttu-id="928b2-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="928b2-122">Data type: string</span></span>  
  
 <span data-ttu-id="928b2-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="928b2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="928b2-124">Схема универсального кода ресурса (URI) для транспорта.</span><span class="sxs-lookup"><span data-stu-id="928b2-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="928b2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="928b2-125">Requirements</span></span>  
  
|<span data-ttu-id="928b2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="928b2-126">MOF</span></span>|<span data-ttu-id="928b2-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="928b2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="928b2-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="928b2-128">Namespace</span></span>|<span data-ttu-id="928b2-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="928b2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="928b2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="928b2-130">See also</span></span>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
