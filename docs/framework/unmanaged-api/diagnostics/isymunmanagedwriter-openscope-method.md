---
title: Метод ISymUnmanagedWriter::OpenScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ccaaee614b1ec4d03271e70338fff82d629a7c28
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468475"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="56cb6-102">Метод ISymUnmanagedWriter::OpenScope</span><span class="sxs-lookup"><span data-stu-id="56cb6-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="56cb6-103">Открывает новую лексическую область видимости в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="56cb6-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="56cb6-104">Область становится новой текущей областью и помещается в стек области.</span><span class="sxs-lookup"><span data-stu-id="56cb6-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="56cb6-105">Области должны образовывать иерархию.</span><span class="sxs-lookup"><span data-stu-id="56cb6-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="56cb6-106">Одноуровневые элементы, не разрешено перекрывать.</span><span class="sxs-lookup"><span data-stu-id="56cb6-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cb6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56cb6-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56cb6-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="56cb6-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="56cb6-109">[in] Смещение первой инструкции в лексической области в байтах от начала метода.</span><span class="sxs-lookup"><span data-stu-id="56cb6-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="56cb6-110">[out] Указатель на `ULONG32` , получающий идентификатор области.</span><span class="sxs-lookup"><span data-stu-id="56cb6-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56cb6-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56cb6-111">Return Value</span></span>  
 <span data-ttu-id="56cb6-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="56cb6-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56cb6-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="56cb6-113">Remarks</span></span>  
 <span data-ttu-id="56cb6-114">`ISymUnmanagedWriter::OpenScope` Возвращает непрозрачный идентификатор области, можно использовать с [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) для определения области начального и конечного смещения в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="56cb6-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="56cb6-115">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="56cb6-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="56cb6-116">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="56cb6-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56cb6-117">Требования</span><span class="sxs-lookup"><span data-stu-id="56cb6-117">Requirements</span></span>  
 <span data-ttu-id="56cb6-118">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="56cb6-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cb6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="56cb6-119">See also</span></span>
- [<span data-ttu-id="56cb6-120">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="56cb6-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
