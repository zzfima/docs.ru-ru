---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145682"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="ccac3-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ccac3-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="ccac3-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ccac3-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccac3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccac3-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ccac3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ccac3-105">Methods</span></span>  
 <span data-ttu-id="ccac3-106">Класс BinaryMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="ccac3-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ccac3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="ccac3-107">Properties</span></span>  
 <span data-ttu-id="ccac3-108">Класс BinaryMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="ccac3-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="ccac3-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="ccac3-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="ccac3-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ccac3-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="ccac3-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ccac3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccac3-112">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="ccac3-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="ccac3-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="ccac3-113">MaxSessionSize</span></span>  
 <span data-ttu-id="ccac3-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ccac3-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ccac3-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ccac3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccac3-116">Значение, указывающее максимальный размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="ccac3-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="ccac3-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="ccac3-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="ccac3-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ccac3-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="ccac3-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ccac3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccac3-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="ccac3-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="ccac3-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ccac3-121">ReaderQuotas</span></span>  
 <span data-ttu-id="ccac3-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ccac3-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="ccac3-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ccac3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccac3-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="ccac3-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccac3-125">Требования</span><span class="sxs-lookup"><span data-stu-id="ccac3-125">Requirements</span></span>  
  
|<span data-ttu-id="ccac3-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ccac3-126">MOF</span></span>|<span data-ttu-id="ccac3-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ccac3-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ccac3-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ccac3-128">Namespace</span></span>|<span data-ttu-id="ccac3-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ccac3-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccac3-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ccac3-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
