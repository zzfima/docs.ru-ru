---
title: Интерфейс ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427435"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="07558-102">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="07558-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="07558-103">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="07558-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="07558-104">Этот интерфейс предоставляет доступ к только связанные с symbol атрибуты метода, вместо атрибутов, связанных с типами.</span><span class="sxs-lookup"><span data-stu-id="07558-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07558-105">Методы</span><span class="sxs-lookup"><span data-stu-id="07558-105">Methods</span></span>  
  
|<span data-ttu-id="07558-106">Метод</span><span class="sxs-lookup"><span data-stu-id="07558-106">Method</span></span>|<span data-ttu-id="07558-107">Описание</span><span class="sxs-lookup"><span data-stu-id="07558-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07558-108">Метод GetNamespace</span><span class="sxs-lookup"><span data-stu-id="07558-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="07558-109">Возвращает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="07558-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="07558-110">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="07558-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="07558-111">Возвращает смещение в этом методе, соответствующее заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="07558-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="07558-112">Метод GetParameters</span><span class="sxs-lookup"><span data-stu-id="07558-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="07558-113">Получает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="07558-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="07558-114">Метод GetRanges</span><span class="sxs-lookup"><span data-stu-id="07558-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="07558-115">Заданной позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам на языке MSIL занимаемым данной позицией в этом методе.</span><span class="sxs-lookup"><span data-stu-id="07558-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="07558-116">Метод GetRootScope</span><span class="sxs-lookup"><span data-stu-id="07558-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="07558-117">Возвращает корневую лексическую область в этом методе.</span><span class="sxs-lookup"><span data-stu-id="07558-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="07558-118">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="07558-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="07558-119">Метод GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="07558-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="07558-120">Возвращает наиболее узкая Внешняя лексическая область в этом методе, содержащую данное смещение.</span><span class="sxs-lookup"><span data-stu-id="07558-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="07558-121">Метод GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="07558-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="07558-122">Возвращает число точек следования в методе.</span><span class="sxs-lookup"><span data-stu-id="07558-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="07558-123">Метод GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="07558-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="07558-124">Возвращает все точки следования в методе.</span><span class="sxs-lookup"><span data-stu-id="07558-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="07558-125">Метод GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="07558-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="07558-126">Возвращает начальную и конечную позицию документа источника этого метода.</span><span class="sxs-lookup"><span data-stu-id="07558-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="07558-127">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="07558-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="07558-128">Возвращает токен метаданных для этого метода.</span><span class="sxs-lookup"><span data-stu-id="07558-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07558-129">Требования</span><span class="sxs-lookup"><span data-stu-id="07558-129">Requirements</span></span>  
 <span data-ttu-id="07558-130">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="07558-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07558-131">См. также</span><span class="sxs-lookup"><span data-stu-id="07558-131">See Also</span></span>  
 [<span data-ttu-id="07558-132">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="07558-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
