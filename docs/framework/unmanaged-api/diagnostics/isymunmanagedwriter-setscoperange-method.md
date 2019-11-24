---
title: Метод ISymUnmanagedWriter::SetScopeRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: b404a187d8628a04d2aa51df15f86fcc9d0b14f8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427860"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="d91c2-102">Метод ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="d91c2-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="d91c2-103">Определяет диапазон смещений для заданной лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="d91c2-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="d91c2-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span><span class="sxs-lookup"><span data-stu-id="d91c2-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="d91c2-105">Scopes must form a hierarchy.</span><span class="sxs-lookup"><span data-stu-id="d91c2-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="d91c2-106">Siblings are not allowed to overlap.</span><span class="sxs-lookup"><span data-stu-id="d91c2-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91c2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d91c2-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d91c2-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d91c2-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="d91c2-109">[in] The scope identifier for the scope.</span><span class="sxs-lookup"><span data-stu-id="d91c2-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="d91c2-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span><span class="sxs-lookup"><span data-stu-id="d91c2-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="d91c2-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span><span class="sxs-lookup"><span data-stu-id="d91c2-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d91c2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d91c2-112">Return Value</span></span>  
 <span data-ttu-id="d91c2-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d91c2-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d91c2-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="d91c2-114">Remarks</span></span>  
 <span data-ttu-id="d91c2-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span><span class="sxs-lookup"><span data-stu-id="d91c2-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="d91c2-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span><span class="sxs-lookup"><span data-stu-id="d91c2-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="d91c2-117">Scope identifiers are only valid in the current method.</span><span class="sxs-lookup"><span data-stu-id="d91c2-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d91c2-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d91c2-118">Requirements</span></span>  
 <span data-ttu-id="d91c2-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d91c2-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91c2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d91c2-120">See also</span></span>

- [<span data-ttu-id="d91c2-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d91c2-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
