---
title: Метод ISymUnmanagedMethod::GetScopeFromOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b036c5cff5300377580fe22dc254911fbdd79715
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503129"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="c95b9-102">Метод ISymUnmanagedMethod::GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="c95b9-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="c95b9-103">Возвращает наиболее узкую внешнюю лексическую область, в этот метод, который окружает заданного смещения.</span><span class="sxs-lookup"><span data-stu-id="c95b9-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="c95b9-104">Это может использоваться для запуска поиска локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c95b9-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95b9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c95b9-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c95b9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c95b9-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="c95b9-107">[in] Объект `ULONG` , содержащий смещение.</span><span class="sxs-lookup"><span data-stu-id="c95b9-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c95b9-108">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c95b9-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c95b9-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c95b9-109">Return Value</span></span>  
 <span data-ttu-id="c95b9-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="c95b9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c95b9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c95b9-111">Requirements</span></span>  
 <span data-ttu-id="c95b9-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c95b9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95b9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c95b9-113">See also</span></span>
- [<span data-ttu-id="c95b9-114">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="c95b9-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
