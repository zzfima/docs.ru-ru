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
ms.openlocfilehash: da50542d9f57e008b31ce2e6ed9698df1275d5eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618815"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="928a8-102">Метод ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="928a8-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="928a8-103">Определяет диапазон смещений для заданной лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="928a8-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="928a8-104">Область становится новой текущей областью и помещается в стек области.</span><span class="sxs-lookup"><span data-stu-id="928a8-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="928a8-105">Области должны образовывать иерархию.</span><span class="sxs-lookup"><span data-stu-id="928a8-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="928a8-106">Одноуровневые элементы, не разрешено перекрывать.</span><span class="sxs-lookup"><span data-stu-id="928a8-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="928a8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="928a8-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="928a8-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="928a8-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="928a8-109">[in] Идентификатор области для области.</span><span class="sxs-lookup"><span data-stu-id="928a8-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="928a8-110">[in] Смещение в байтах первой инструкции в лексической области в начале метода.</span><span class="sxs-lookup"><span data-stu-id="928a8-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="928a8-111">[in] Смещение в байтах последней инструкции в лексической области в начале метода.</span><span class="sxs-lookup"><span data-stu-id="928a8-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="928a8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="928a8-112">Return Value</span></span>  
 <span data-ttu-id="928a8-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="928a8-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="928a8-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="928a8-114">Remarks</span></span>  
 <span data-ttu-id="928a8-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, можно использовать с `ISymUnmanagedWriter::SetScopeRange` для определения области начального и конечного смещения в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="928a8-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="928a8-116">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="928a8-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="928a8-117">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="928a8-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="928a8-118">Требования</span><span class="sxs-lookup"><span data-stu-id="928a8-118">Requirements</span></span>  
 <span data-ttu-id="928a8-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="928a8-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="928a8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="928a8-120">See also</span></span>
- [<span data-ttu-id="928a8-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="928a8-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
