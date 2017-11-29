---
title: "Метод ISymUnmanagedWriter::OpenScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f56bc14b096b5086db1fc8d046ed699559381fb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="1a5d4-102">Метод ISymUnmanagedWriter::OpenScope</span><span class="sxs-lookup"><span data-stu-id="1a5d4-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="1a5d4-103">Открывает новую лексическую область видимости в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="1a5d4-104">Область становится новой текущей областью и помещается в стек областей.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="1a5d4-105">Области должны образовывать иерархию.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="1a5d4-106">Перекрытие элементов с общим родителем запрещено.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5d4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a5d4-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a5d4-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a5d4-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="1a5d4-109">[in] Смещение первой инструкции в лексической области видимости, в байтах от начала метода.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1a5d4-110">[out] Указатель на `ULONG32` , получающий идентификатор области.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a5d4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a5d4-111">Return Value</span></span>  
 <span data-ttu-id="1a5d4-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a5d4-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a5d4-113">Remarks</span></span>  
 <span data-ttu-id="1a5d4-114">`ISymUnmanagedWriter::OpenScope`Возвращает непрозрачный идентификатор области, можно использовать с [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) для определения области начального и конечного смещения в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="1a5d4-115">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="1a5d4-116">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="1a5d4-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5d4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="1a5d4-117">Requirements</span></span>  
 <span data-ttu-id="1a5d4-118">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a5d4-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5d4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1a5d4-119">See Also</span></span>  
 [<span data-ttu-id="1a5d4-120">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1a5d4-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
