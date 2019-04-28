---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 67c1083daa9acfd204d4de50d4e9178b25aafcf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858394"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="53174-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="53174-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="53174-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="53174-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53174-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53174-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="53174-105">Методы</span><span class="sxs-lookup"><span data-stu-id="53174-105">Methods</span></span>  
 <span data-ttu-id="53174-106">Класс TextMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="53174-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="53174-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="53174-107">Properties</span></span>  
 <span data-ttu-id="53174-108">Класс TextMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="53174-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="53174-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="53174-109">Encoding</span></span>  
 <span data-ttu-id="53174-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="53174-110">Data type: string</span></span>  
  
 <span data-ttu-id="53174-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="53174-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53174-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="53174-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="53174-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="53174-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="53174-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="53174-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="53174-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="53174-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53174-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="53174-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="53174-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="53174-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="53174-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="53174-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="53174-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="53174-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53174-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="53174-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="53174-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="53174-121">ReaderQuotas</span></span>  
 <span data-ttu-id="53174-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="53174-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="53174-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="53174-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53174-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="53174-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53174-125">Требования</span><span class="sxs-lookup"><span data-stu-id="53174-125">Requirements</span></span>  
  
|<span data-ttu-id="53174-126">MOF</span><span class="sxs-lookup"><span data-stu-id="53174-126">MOF</span></span>|<span data-ttu-id="53174-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="53174-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="53174-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="53174-128">Namespace</span></span>|<span data-ttu-id="53174-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="53174-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53174-130">См. также</span><span class="sxs-lookup"><span data-stu-id="53174-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
