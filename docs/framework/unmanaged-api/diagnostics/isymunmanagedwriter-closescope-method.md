---
title: "Метод ISymUnmanagedWriter::CloseScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d47be1d220729ed32fcf77a77e611003085c15d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="f3d59-102">Метод ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="f3d59-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="f3d59-103">Закрывает текущую лексическую область видимости.</span><span class="sxs-lookup"><span data-stu-id="f3d59-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d59-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3d59-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3d59-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3d59-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="f3d59-106">[in] Смещение от начала метода точки в конце последней инструкции в лексической области видимости, в байтах.</span><span class="sxs-lookup"><span data-stu-id="f3d59-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3d59-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f3d59-107">Return Value</span></span>  
 <span data-ttu-id="f3d59-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="f3d59-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d59-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3d59-109">Remarks</span></span>  
 <span data-ttu-id="f3d59-110">После закрытия области нельзя определять дополнительные переменные не внутри нее.</span><span class="sxs-lookup"><span data-stu-id="f3d59-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="f3d59-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, можно использовать с [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) для определения области позже начального и конечного смещения.</span><span class="sxs-lookup"><span data-stu-id="f3d59-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="f3d59-112">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="f3d59-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="f3d59-113">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="f3d59-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d59-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f3d59-114">Requirements</span></span>  
 <span data-ttu-id="f3d59-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3d59-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d59-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d59-116">See Also</span></span>  
 [<span data-ttu-id="f3d59-117">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f3d59-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
