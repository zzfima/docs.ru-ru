---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 49a640a666131491366646d6d486d25a515e35bf
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373436"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="687af-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="687af-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="687af-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="687af-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="687af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="687af-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="687af-105">Методы</span><span class="sxs-lookup"><span data-stu-id="687af-105">Methods</span></span>  
 <span data-ttu-id="687af-106">Класс MtomMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="687af-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="687af-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="687af-107">Properties</span></span>  
 <span data-ttu-id="687af-108">Класс MtomMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="687af-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="687af-109">кодировка</span><span class="sxs-lookup"><span data-stu-id="687af-109">Encoding</span></span>  
 <span data-ttu-id="687af-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="687af-110">Data type: string</span></span>  
  
 <span data-ttu-id="687af-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="687af-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="687af-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="687af-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="687af-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="687af-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="687af-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="687af-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="687af-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="687af-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="687af-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="687af-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="687af-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="687af-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="687af-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="687af-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="687af-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="687af-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="687af-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="687af-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="687af-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="687af-121">ReaderQuotas</span></span>  
 <span data-ttu-id="687af-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="687af-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="687af-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="687af-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="687af-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="687af-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="687af-125">Требования</span><span class="sxs-lookup"><span data-stu-id="687af-125">Requirements</span></span>  
  
|<span data-ttu-id="687af-126">MOF</span><span class="sxs-lookup"><span data-stu-id="687af-126">MOF</span></span>|<span data-ttu-id="687af-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="687af-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="687af-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="687af-128">Namespace</span></span>|<span data-ttu-id="687af-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="687af-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="687af-130">См. также</span><span class="sxs-lookup"><span data-stu-id="687af-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
