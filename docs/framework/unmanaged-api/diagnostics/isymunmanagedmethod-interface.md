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
ms.openlocfilehash: c29656a4787c674886505a3be2508470460dfc10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939533"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="6730c-102">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="6730c-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="6730c-103">Представляет метод, в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="6730c-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="6730c-104">Этот интерфейс предоставляет доступ к только связанные с symbol атрибуты метода, вместо атрибутов, связанных с типом.</span><span class="sxs-lookup"><span data-stu-id="6730c-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6730c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6730c-105">Methods</span></span>  
  
|<span data-ttu-id="6730c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6730c-106">Method</span></span>|<span data-ttu-id="6730c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6730c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6730c-108">Метод GetNamespace</span><span class="sxs-lookup"><span data-stu-id="6730c-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="6730c-109">Получает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="6730c-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="6730c-110">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="6730c-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="6730c-111">Возвращает смещение в этом методе, соответствующее данной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="6730c-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="6730c-112">Метод GetParameters</span><span class="sxs-lookup"><span data-stu-id="6730c-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="6730c-113">Получает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="6730c-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="6730c-114">Метод GetRanges</span><span class="sxs-lookup"><span data-stu-id="6730c-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="6730c-115">Возвращает массив пар начального и конечного смещения, соответствующих диапазонам на языке MSIL, занимаемым позиция в этом методе обозначение позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="6730c-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="6730c-116">Метод GetRootScope</span><span class="sxs-lookup"><span data-stu-id="6730c-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="6730c-117">Возвращает корневую лексическую область, в этом методе.</span><span class="sxs-lookup"><span data-stu-id="6730c-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="6730c-118">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="6730c-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="6730c-119">Метод GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="6730c-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="6730c-120">Возвращает наиболее узкую внешнюю лексическую область, в этот метод, который окружает заданного смещения.</span><span class="sxs-lookup"><span data-stu-id="6730c-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="6730c-121">Метод GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="6730c-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="6730c-122">Возвращает число точек следования в этот метод.</span><span class="sxs-lookup"><span data-stu-id="6730c-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="6730c-123">Метод GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="6730c-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="6730c-124">Возвращает все точки следования в методе.</span><span class="sxs-lookup"><span data-stu-id="6730c-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="6730c-125">Метод GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="6730c-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="6730c-126">Получает начальное и конечное положение документа для источника этого метода.</span><span class="sxs-lookup"><span data-stu-id="6730c-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="6730c-127">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="6730c-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="6730c-128">Возвращает маркер метаданных для этого метода.</span><span class="sxs-lookup"><span data-stu-id="6730c-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6730c-129">Требования</span><span class="sxs-lookup"><span data-stu-id="6730c-129">Requirements</span></span>  
 <span data-ttu-id="6730c-130">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6730c-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6730c-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6730c-131">See also</span></span>

- [<span data-ttu-id="6730c-132">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="6730c-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
