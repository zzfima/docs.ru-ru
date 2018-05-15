---
title: Метод ISymUnmanagedScope::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19d116825efc4eb2ec1de22f232f46f8fb0fdf18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="92967-102">Метод ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="92967-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="92967-103">Возвращает начальное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="92967-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92967-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92967-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92967-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92967-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="92967-106">[out] Указатель на `ULONG32` , содержащий начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="92967-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92967-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="92967-107">Return Value</span></span>  
 <span data-ttu-id="92967-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="92967-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92967-109">Требования</span><span class="sxs-lookup"><span data-stu-id="92967-109">Requirements</span></span>  
 <span data-ttu-id="92967-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="92967-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92967-111">См. также</span><span class="sxs-lookup"><span data-stu-id="92967-111">See Also</span></span>  
 [<span data-ttu-id="92967-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="92967-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="92967-113">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="92967-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
