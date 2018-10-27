---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: 326fe6a7ca8dc5dba0dd64b1c5fc97cec49279c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180891"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="d94d9-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d94d9-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="d94d9-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d94d9-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d94d9-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d94d9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d94d9-105">Methods</span></span>  
 <span data-ttu-id="d94d9-106">Класс BinaryMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d94d9-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d94d9-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d94d9-107">Properties</span></span>  
 <span data-ttu-id="d94d9-108">Класс BinaryMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d94d9-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="d94d9-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d94d9-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="d94d9-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="d94d9-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="d94d9-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d94d9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94d9-112">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="d94d9-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="d94d9-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="d94d9-113">MaxSessionSize</span></span>  
 <span data-ttu-id="d94d9-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="d94d9-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d94d9-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d94d9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94d9-116">Значение, указывающее максимальный размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="d94d9-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="d94d9-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d94d9-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="d94d9-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="d94d9-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d94d9-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d94d9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94d9-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="d94d9-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="d94d9-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d94d9-121">ReaderQuotas</span></span>  
 <span data-ttu-id="d94d9-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d94d9-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="d94d9-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d94d9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94d9-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="d94d9-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d94d9-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d94d9-125">Requirements</span></span>  
  
|<span data-ttu-id="d94d9-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d94d9-126">MOF</span></span>|<span data-ttu-id="d94d9-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d94d9-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d94d9-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d94d9-128">Namespace</span></span>|<span data-ttu-id="d94d9-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d94d9-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d94d9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d94d9-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
