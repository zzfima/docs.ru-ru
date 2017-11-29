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
ms.openlocfilehash: a8df22e5f9ea2ca294f502fcebf4b2ed5cd7900d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="41669-102">Метод ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="41669-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="41669-103">Закрывает текущую лексическую область видимости.</span><span class="sxs-lookup"><span data-stu-id="41669-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41669-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41669-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41669-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41669-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="41669-106">[in] Смещение от начала метода точки в конце последней инструкции в лексической области видимости, в байтах.</span><span class="sxs-lookup"><span data-stu-id="41669-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41669-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="41669-107">Return Value</span></span>  
 <span data-ttu-id="41669-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="41669-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41669-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="41669-109">Remarks</span></span>  
 <span data-ttu-id="41669-110">После закрытия области нельзя определять дополнительные переменные не внутри нее.</span><span class="sxs-lookup"><span data-stu-id="41669-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="41669-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, можно использовать с [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) для определения области позже начального и конечного смещения.</span><span class="sxs-lookup"><span data-stu-id="41669-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="41669-112">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="41669-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="41669-113">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="41669-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41669-114">Требования</span><span class="sxs-lookup"><span data-stu-id="41669-114">Requirements</span></span>  
 <span data-ttu-id="41669-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="41669-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41669-116">См. также</span><span class="sxs-lookup"><span data-stu-id="41669-116">See Also</span></span>  
 [<span data-ttu-id="41669-117">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="41669-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
