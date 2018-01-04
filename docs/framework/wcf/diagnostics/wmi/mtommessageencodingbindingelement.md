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
ms.workload: dotnet
ms.openlocfilehash: 3cc36d7daed1a2cfaf050cbfe9661951117ff66d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="ffbff-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ffbff-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="ffbff-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ffbff-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffbff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffbff-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ffbff-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ffbff-105">Methods</span></span>  
 <span data-ttu-id="ffbff-106">Класс MtomMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="ffbff-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ffbff-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="ffbff-107">Properties</span></span>  
 <span data-ttu-id="ffbff-108">Класс MtomMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="ffbff-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="ffbff-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="ffbff-109">Encoding</span></span>  
 <span data-ttu-id="ffbff-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="ffbff-110">Data type: string</span></span>  
  
 <span data-ttu-id="ffbff-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ffbff-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ffbff-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="ffbff-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="ffbff-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="ffbff-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="ffbff-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ffbff-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ffbff-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ffbff-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ffbff-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="ffbff-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="ffbff-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="ffbff-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="ffbff-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ffbff-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="ffbff-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ffbff-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ffbff-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="ffbff-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="ffbff-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ffbff-121">ReaderQuotas</span></span>  
 <span data-ttu-id="ffbff-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ffbff-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="ffbff-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ffbff-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ffbff-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="ffbff-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffbff-125">Требования</span><span class="sxs-lookup"><span data-stu-id="ffbff-125">Requirements</span></span>  
  
|<span data-ttu-id="ffbff-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ffbff-126">MOF</span></span>|<span data-ttu-id="ffbff-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ffbff-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ffbff-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ffbff-128">Namespace</span></span>|<span data-ttu-id="ffbff-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ffbff-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffbff-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ffbff-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
