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
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449103"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="d8629-102">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="d8629-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="d8629-103">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d8629-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="d8629-104">Документ определяется по универсальному указателю ресурсов (URL-адрес) и GUID типа документа.</span><span class="sxs-lookup"><span data-stu-id="d8629-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="d8629-105">Документ можно разместить независимо от того, как он хранится, используя URL-адрес и GUID типа документа.</span><span class="sxs-lookup"><span data-stu-id="d8629-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="d8629-106">Вы можете сохранить источник документа в хранилище символов и получить его через этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d8629-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8629-107">Методы</span><span class="sxs-lookup"><span data-stu-id="d8629-107">Methods</span></span>  
  
|<span data-ttu-id="d8629-108">Метод</span><span class="sxs-lookup"><span data-stu-id="d8629-108">Method</span></span>|<span data-ttu-id="d8629-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d8629-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8629-110">Метод FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="d8629-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="d8629-111">Возвращает ближайшую строку, которая является точкой последовательности, с учетом строки в этом документе, которая может быть или не являться точкой последовательности.</span><span class="sxs-lookup"><span data-stu-id="d8629-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="d8629-112">Метод GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="d8629-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="d8629-113">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="d8629-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="d8629-114">Метод GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="d8629-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="d8629-115">Возвращает идентификатор алгоритма контрольной суммы или возвращает идентификатор GUID всех нулей, если контрольная сумма отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d8629-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="d8629-116">Метод GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="d8629-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="d8629-117">Возвращает тип документа этого документа.</span><span class="sxs-lookup"><span data-stu-id="d8629-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="d8629-118">Метод GetLanguage</span><span class="sxs-lookup"><span data-stu-id="d8629-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="d8629-119">Возвращает идентификатор языка этого документа.</span><span class="sxs-lookup"><span data-stu-id="d8629-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="d8629-120">Метод GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="d8629-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="d8629-121">Получает поставщика языка этого документа.</span><span class="sxs-lookup"><span data-stu-id="d8629-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="d8629-122">Метод GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="d8629-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="d8629-123">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="d8629-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="d8629-124">Метод GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="d8629-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="d8629-125">Возвращает указанный диапазон внедренного источника в заданный буфер.</span><span class="sxs-lookup"><span data-stu-id="d8629-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="d8629-126">Метод GetURL</span><span class="sxs-lookup"><span data-stu-id="d8629-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="d8629-127">Возвращает URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="d8629-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="d8629-128">Метод HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="d8629-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="d8629-129">Возвращает `true`, если документ содержит исходный код, внедренный в отладочные символы; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="d8629-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8629-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d8629-130">See also</span></span>

- [<span data-ttu-id="d8629-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d8629-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
