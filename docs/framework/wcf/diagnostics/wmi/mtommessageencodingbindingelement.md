---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 83fa879fbef94e2dc9c142dfb92a51a54a7b60cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486538"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="fe557-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="fe557-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="fe557-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="fe557-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe557-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe557-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fe557-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fe557-105">Methods</span></span>  
 <span data-ttu-id="fe557-106">Класс MtomMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="fe557-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fe557-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="fe557-107">Properties</span></span>  
 <span data-ttu-id="fe557-108">Класс MtomMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="fe557-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="fe557-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="fe557-109">Encoding</span></span>  
 <span data-ttu-id="fe557-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="fe557-110">Data type: string</span></span>  
  
 <span data-ttu-id="fe557-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fe557-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe557-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="fe557-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="fe557-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="fe557-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="fe557-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="fe557-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe557-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fe557-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe557-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="fe557-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="fe557-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="fe557-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="fe557-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="fe557-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe557-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fe557-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe557-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="fe557-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="fe557-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="fe557-121">ReaderQuotas</span></span>  
 <span data-ttu-id="fe557-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="fe557-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="fe557-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fe557-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe557-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="fe557-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe557-125">Требования</span><span class="sxs-lookup"><span data-stu-id="fe557-125">Requirements</span></span>  
  
|<span data-ttu-id="fe557-126">MOF</span><span class="sxs-lookup"><span data-stu-id="fe557-126">MOF</span></span>|<span data-ttu-id="fe557-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fe557-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fe557-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="fe557-128">Namespace</span></span>|<span data-ttu-id="fe557-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="fe557-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe557-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fe557-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
