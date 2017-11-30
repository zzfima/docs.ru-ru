---
title: "Интерфейс ISymUnmanagedMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod
helpviewer_keywords: ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 030ea4b472f6a6aead307e0c5cc94dfb34c19992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="6cf5d-102">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="6cf5d-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="6cf5d-103">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="6cf5d-104">Этот интерфейс предоставляет доступ к только связанные с symbol атрибуты метода, вместо атрибутов, связанных с типами.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6cf5d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6cf5d-105">Methods</span></span>  
  
|<span data-ttu-id="6cf5d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6cf5d-106">Method</span></span>|<span data-ttu-id="6cf5d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6cf5d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6cf5d-108">Метод GetNamespace</span><span class="sxs-lookup"><span data-stu-id="6cf5d-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="6cf5d-109">Возвращает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="6cf5d-110">GetOffset-метод</span><span class="sxs-lookup"><span data-stu-id="6cf5d-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="6cf5d-111">Возвращает смещение в этом методе, соответствующее заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="6cf5d-112">Метод GetParameters</span><span class="sxs-lookup"><span data-stu-id="6cf5d-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="6cf5d-113">Получает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="6cf5d-114">Метод GetRanges</span><span class="sxs-lookup"><span data-stu-id="6cf5d-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="6cf5d-115">Заданной позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам на языке MSIL занимаемым данной позицией в этом методе.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="6cf5d-116">Метод GetRootScope</span><span class="sxs-lookup"><span data-stu-id="6cf5d-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="6cf5d-117">Возвращает корневую лексическую область в этом методе.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="6cf5d-118">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="6cf5d-119">Метод GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="6cf5d-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="6cf5d-120">Возвращает наиболее узкая Внешняя лексическая область в этом методе, содержащую данное смещение.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="6cf5d-121">Метод GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="6cf5d-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="6cf5d-122">Возвращает число точек следования в методе.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="6cf5d-123">Метод GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="6cf5d-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="6cf5d-124">Возвращает все точки следования в методе.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="6cf5d-125">Метод GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="6cf5d-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="6cf5d-126">Возвращает начальную и конечную позицию документа источника этого метода.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="6cf5d-127">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="6cf5d-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="6cf5d-128">Возвращает токен метаданных для этого метода.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6cf5d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="6cf5d-129">Requirements</span></span>  
 <span data-ttu-id="6cf5d-130">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6cf5d-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf5d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6cf5d-131">See Also</span></span>  
 [<span data-ttu-id="6cf5d-132">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="6cf5d-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
