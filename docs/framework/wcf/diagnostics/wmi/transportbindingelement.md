---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112376"
---
# <a name="transportbindingelement"></a><span data-ttu-id="0d109-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0d109-102">TransportBindingElement</span></span>
<span data-ttu-id="0d109-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0d109-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d109-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d109-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0d109-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0d109-105">Methods</span></span>  
 <span data-ttu-id="0d109-106">Класс TransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="0d109-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0d109-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="0d109-107">Properties</span></span>  
 <span data-ttu-id="0d109-108">Класс TransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0d109-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="0d109-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="0d109-109">ManualAddressing</span></span>  
 <span data-ttu-id="0d109-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0d109-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0d109-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0d109-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d109-112">Логическое значение, указывающее, требуется ли пользователю контролировать адресацию сообщений.</span><span class="sxs-lookup"><span data-stu-id="0d109-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="0d109-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="0d109-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="0d109-114">Тип данных: sint64</span><span class="sxs-lookup"><span data-stu-id="0d109-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="0d109-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0d109-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d109-116">Максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="0d109-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="0d109-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="0d109-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="0d109-118">Тип данных: sint64</span><span class="sxs-lookup"><span data-stu-id="0d109-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="0d109-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0d109-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d109-120">Максимально размер сообщения, обрабатываемого данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="0d109-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="0d109-121">Схема</span><span class="sxs-lookup"><span data-stu-id="0d109-121">Scheme</span></span>  
 <span data-ttu-id="0d109-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0d109-122">Data type: string</span></span>  
  
 <span data-ttu-id="0d109-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0d109-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d109-124">Схема универсального кода ресурса (URI) для транспорта.</span><span class="sxs-lookup"><span data-stu-id="0d109-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d109-125">Требования</span><span class="sxs-lookup"><span data-stu-id="0d109-125">Requirements</span></span>  
  
|<span data-ttu-id="0d109-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0d109-126">MOF</span></span>|<span data-ttu-id="0d109-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0d109-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0d109-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0d109-128">Namespace</span></span>|<span data-ttu-id="0d109-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0d109-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d109-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0d109-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
