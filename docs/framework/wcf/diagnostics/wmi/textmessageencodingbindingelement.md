---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f1e026296745f6fc40171866c81f91818789e01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="6c1a3-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="6c1a3-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="6c1a3-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="6c1a3-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c1a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c1a3-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6c1a3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6c1a3-105">Methods</span></span>  
 <span data-ttu-id="6c1a3-106">Класс TextMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6c1a3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6c1a3-107">Properties</span></span>  
 <span data-ttu-id="6c1a3-108">Класс TextMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="6c1a3-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="6c1a3-109">Encoding</span></span>  
 <span data-ttu-id="6c1a3-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6c1a3-110">Data type: string</span></span>  
  
 <span data-ttu-id="6c1a3-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="6c1a3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c1a3-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="6c1a3-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="6c1a3-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="6c1a3-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="6c1a3-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="6c1a3-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="6c1a3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c1a3-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="6c1a3-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="6c1a3-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="6c1a3-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="6c1a3-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="6c1a3-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="6c1a3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c1a3-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="6c1a3-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="6c1a3-121">ReaderQuotas</span></span>  
 <span data-ttu-id="6c1a3-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="6c1a3-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="6c1a3-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="6c1a3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c1a3-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c1a3-125">Требования</span><span class="sxs-lookup"><span data-stu-id="6c1a3-125">Requirements</span></span>  
  
|<span data-ttu-id="6c1a3-126">MOF</span><span class="sxs-lookup"><span data-stu-id="6c1a3-126">MOF</span></span>|<span data-ttu-id="6c1a3-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6c1a3-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6c1a3-128">Namespace</span></span>|<span data-ttu-id="6c1a3-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6c1a3-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c1a3-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6c1a3-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
