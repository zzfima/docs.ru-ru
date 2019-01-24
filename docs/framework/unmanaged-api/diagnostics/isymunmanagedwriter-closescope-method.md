---
title: Метод ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e33d69e319d7817a54dca76526b6c3ee9bb6384f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729974"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="36aaf-102">Метод ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="36aaf-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="36aaf-103">Закрывает текущую лексическую область видимости.</span><span class="sxs-lookup"><span data-stu-id="36aaf-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36aaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36aaf-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36aaf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36aaf-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="36aaf-106">[in] Смещение от начала метода точки в конце последней инструкции в лексической области в байтах.</span><span class="sxs-lookup"><span data-stu-id="36aaf-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36aaf-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="36aaf-107">Return Value</span></span>  
 <span data-ttu-id="36aaf-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="36aaf-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36aaf-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="36aaf-109">Remarks</span></span>  
 <span data-ttu-id="36aaf-110">После закрытия области, дополнительные переменные не могут определяться внутри него.</span><span class="sxs-lookup"><span data-stu-id="36aaf-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="36aaf-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, можно использовать с [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) для более поздней версии определения области начального и конечного смещения.</span><span class="sxs-lookup"><span data-stu-id="36aaf-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="36aaf-112">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="36aaf-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="36aaf-113">Идентификаторы областей действительны только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="36aaf-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36aaf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="36aaf-114">Requirements</span></span>  
 <span data-ttu-id="36aaf-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="36aaf-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36aaf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="36aaf-116">See also</span></span>
- [<span data-ttu-id="36aaf-117">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="36aaf-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
