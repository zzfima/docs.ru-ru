---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 867b4a2b84a28dff4e3b9e4fc9d3c52065de212f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="baed6-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="baed6-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="baed6-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="baed6-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baed6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baed6-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="baed6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="baed6-105">Methods</span></span>  
 <span data-ttu-id="baed6-106">Класс MtomMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="baed6-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="baed6-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="baed6-107">Properties</span></span>  
 <span data-ttu-id="baed6-108">Класс MtomMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="baed6-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="baed6-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="baed6-109">Encoding</span></span>  
 <span data-ttu-id="baed6-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="baed6-110">Data type: string</span></span>  
  
 <span data-ttu-id="baed6-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="baed6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="baed6-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="baed6-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="baed6-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="baed6-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="baed6-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="baed6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="baed6-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="baed6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="baed6-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="baed6-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="baed6-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="baed6-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="baed6-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="baed6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="baed6-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="baed6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="baed6-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="baed6-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="baed6-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="baed6-121">ReaderQuotas</span></span>  
 <span data-ttu-id="baed6-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="baed6-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="baed6-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="baed6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="baed6-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="baed6-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baed6-125">Требования</span><span class="sxs-lookup"><span data-stu-id="baed6-125">Requirements</span></span>  
  
|<span data-ttu-id="baed6-126">MOF</span><span class="sxs-lookup"><span data-stu-id="baed6-126">MOF</span></span>|<span data-ttu-id="baed6-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="baed6-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="baed6-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="baed6-128">Namespace</span></span>|<span data-ttu-id="baed6-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="baed6-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="baed6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="baed6-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
