---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: f9b94e946413967cc14282e85743a23327683b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="d5149-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5149-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="d5149-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5149-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5149-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5149-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d5149-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d5149-105">Methods</span></span>  
 <span data-ttu-id="d5149-106">Класс TextMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d5149-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d5149-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d5149-107">Properties</span></span>  
 <span data-ttu-id="d5149-108">Класс TextMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d5149-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="d5149-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="d5149-109">Encoding</span></span>  
 <span data-ttu-id="d5149-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d5149-110">Data type: string</span></span>  
  
 <span data-ttu-id="d5149-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d5149-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d5149-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="d5149-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="d5149-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d5149-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="d5149-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="d5149-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d5149-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d5149-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d5149-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="d5149-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="d5149-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d5149-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="d5149-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="d5149-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d5149-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d5149-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d5149-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="d5149-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="d5149-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d5149-121">ReaderQuotas</span></span>  
 <span data-ttu-id="d5149-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d5149-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="d5149-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d5149-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d5149-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="d5149-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5149-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d5149-125">Requirements</span></span>  
  
|<span data-ttu-id="d5149-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d5149-126">MOF</span></span>|<span data-ttu-id="d5149-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d5149-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d5149-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d5149-128">Namespace</span></span>|<span data-ttu-id="d5149-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d5149-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5149-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d5149-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
