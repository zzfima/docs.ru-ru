---
title: BinaryMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: adac65808853ec75e37245c8c9fa031a533c22a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="da4c5-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="da4c5-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="da4c5-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="da4c5-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da4c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da4c5-104">Syntax</span></span>  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="da4c5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="da4c5-105">Methods</span></span>  
 <span data-ttu-id="da4c5-106">Класс BinaryMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="da4c5-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="da4c5-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="da4c5-107">Properties</span></span>  
 <span data-ttu-id="da4c5-108">Класс BinaryMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="da4c5-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="da4c5-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="da4c5-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="da4c5-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="da4c5-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="da4c5-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da4c5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da4c5-112">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="da4c5-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="da4c5-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="da4c5-113">MaxSessionSize</span></span>  
 <span data-ttu-id="da4c5-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="da4c5-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="da4c5-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da4c5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da4c5-116">Значение, указывающее максимальный размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="da4c5-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="da4c5-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="da4c5-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="da4c5-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="da4c5-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="da4c5-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da4c5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da4c5-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="da4c5-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="da4c5-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="da4c5-121">ReaderQuotas</span></span>  
 <span data-ttu-id="da4c5-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="da4c5-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="da4c5-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da4c5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da4c5-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="da4c5-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da4c5-125">Требования</span><span class="sxs-lookup"><span data-stu-id="da4c5-125">Requirements</span></span>  
  
|<span data-ttu-id="da4c5-126">MOF</span><span class="sxs-lookup"><span data-stu-id="da4c5-126">MOF</span></span>|<span data-ttu-id="da4c5-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="da4c5-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="da4c5-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="da4c5-128">Namespace</span></span>|<span data-ttu-id="da4c5-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="da4c5-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da4c5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="da4c5-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
