---
title: Интерфейс ISymUnmanagedDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33213aced635549dd439cf679d89367a71baa7c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168809"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="5df12-102">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="5df12-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="5df12-103">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="5df12-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="5df12-104">Документ определяется локатора универсальный код ресурса (URL-адрес) и GUID типа документа.</span><span class="sxs-lookup"><span data-stu-id="5df12-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="5df12-105">Можно найти документ независимо от того, как они хранятся с помощью URL-адрес и идентификатор GUID типа документа.</span><span class="sxs-lookup"><span data-stu-id="5df12-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="5df12-106">Можно сохранить в хранилище символов источник документа и получить его через этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5df12-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5df12-107">Методы</span><span class="sxs-lookup"><span data-stu-id="5df12-107">Methods</span></span>  
  
|<span data-ttu-id="5df12-108">Метод</span><span class="sxs-lookup"><span data-stu-id="5df12-108">Method</span></span>|<span data-ttu-id="5df12-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5df12-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5df12-110">Метод FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="5df12-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="5df12-111">Возвращает ближайшую строку, являющуюся точкой следования, для заданной строки в этом документе, которые могут поддерживаться или не может являться точкой следования.</span><span class="sxs-lookup"><span data-stu-id="5df12-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="5df12-112">Метод GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="5df12-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="5df12-113">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="5df12-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="5df12-114">Метод GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="5df12-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="5df12-115">Возвращает идентификатор алгоритма контрольной суммы, или возвращает идентификатор GUID изо всех нулей, если контрольная сумма отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5df12-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="5df12-116">Метод GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="5df12-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="5df12-117">Получает тип документа в этом документе.</span><span class="sxs-lookup"><span data-stu-id="5df12-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="5df12-118">Метод GetLanguage</span><span class="sxs-lookup"><span data-stu-id="5df12-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="5df12-119">Получает идентификатор языка в этом документе.</span><span class="sxs-lookup"><span data-stu-id="5df12-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="5df12-120">Метод GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="5df12-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="5df12-121">Возвращает поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="5df12-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="5df12-122">Метод GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="5df12-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="5df12-123">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="5df12-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="5df12-124">Метод GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="5df12-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="5df12-125">Возвращает заданный диапазон внедренного источника в заданный буфер.</span><span class="sxs-lookup"><span data-stu-id="5df12-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="5df12-126">Метод GetURL</span><span class="sxs-lookup"><span data-stu-id="5df12-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="5df12-127">Возвращает URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="5df12-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="5df12-128">Метод HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="5df12-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="5df12-129">Возвращает `true` , содержит ли документ источника, внедренный в символы отладки; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="5df12-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5df12-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5df12-130">See also</span></span>

- [<span data-ttu-id="5df12-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5df12-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
