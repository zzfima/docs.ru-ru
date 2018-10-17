---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 2371c38aebe2bd8d6da93d702801556fad986ef9
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372234"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="55ba2-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="55ba2-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="55ba2-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="55ba2-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ba2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55ba2-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="55ba2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="55ba2-105">Methods</span></span>  
 <span data-ttu-id="55ba2-106">Класс TextMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="55ba2-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="55ba2-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="55ba2-107">Properties</span></span>  
 <span data-ttu-id="55ba2-108">Класс TextMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="55ba2-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="55ba2-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="55ba2-109">Encoding</span></span>  
 <span data-ttu-id="55ba2-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="55ba2-110">Data type: string</span></span>  
  
 <span data-ttu-id="55ba2-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="55ba2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55ba2-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="55ba2-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="55ba2-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="55ba2-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="55ba2-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="55ba2-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="55ba2-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="55ba2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55ba2-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="55ba2-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="55ba2-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="55ba2-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="55ba2-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="55ba2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="55ba2-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="55ba2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55ba2-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="55ba2-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="55ba2-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="55ba2-121">ReaderQuotas</span></span>  
 <span data-ttu-id="55ba2-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="55ba2-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="55ba2-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="55ba2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55ba2-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="55ba2-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55ba2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="55ba2-125">Requirements</span></span>  
  
|<span data-ttu-id="55ba2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="55ba2-126">MOF</span></span>|<span data-ttu-id="55ba2-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="55ba2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="55ba2-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="55ba2-128">Namespace</span></span>|<span data-ttu-id="55ba2-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="55ba2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55ba2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="55ba2-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
