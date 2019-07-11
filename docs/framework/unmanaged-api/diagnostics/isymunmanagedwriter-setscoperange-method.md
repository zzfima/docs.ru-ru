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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c13eb7ca16cdb7c70f3fef0dd4efcb9362cd3d87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776593"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="c42c8-102">Метод ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="c42c8-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="c42c8-103">Определяет диапазон смещений для заданной лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="c42c8-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="c42c8-104">Область становится новой текущей областью и помещается в стек области.</span><span class="sxs-lookup"><span data-stu-id="c42c8-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="c42c8-105">Области должны образовывать иерархию.</span><span class="sxs-lookup"><span data-stu-id="c42c8-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="c42c8-106">Одноуровневые элементы, не разрешено перекрывать.</span><span class="sxs-lookup"><span data-stu-id="c42c8-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c42c8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c42c8-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c42c8-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c42c8-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="c42c8-109">[in] Идентификатор области для области.</span><span class="sxs-lookup"><span data-stu-id="c42c8-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="c42c8-110">[in] Смещение в байтах первой инструкции в лексической области в начале метода.</span><span class="sxs-lookup"><span data-stu-id="c42c8-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="c42c8-111">[in] Смещение в байтах последней инструкции в лексической области в начале метода.</span><span class="sxs-lookup"><span data-stu-id="c42c8-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c42c8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c42c8-112">Return Value</span></span>  
 <span data-ttu-id="c42c8-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="c42c8-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c42c8-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c42c8-114">Remarks</span></span>  
 <span data-ttu-id="c42c8-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, можно использовать с `ISymUnmanagedWriter::SetScopeRange` для определения области начального и конечного смещения в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="c42c8-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="c42c8-116">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="c42c8-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="c42c8-117">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="c42c8-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c42c8-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c42c8-118">Requirements</span></span>  
 <span data-ttu-id="c42c8-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c42c8-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42c8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c42c8-120">See also</span></span>

- [<span data-ttu-id="c42c8-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c42c8-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
