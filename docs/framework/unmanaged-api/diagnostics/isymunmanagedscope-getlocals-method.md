---
title: Метод ISymUnmanagedScope::GetLocals
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 781111db30ae664c9dd45744f88387e161f2716f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="bb1f1-102">Метод ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="bb1f1-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="bb1f1-103">Возвращает локальные переменные, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="bb1f1-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb1f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb1f1-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb1f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb1f1-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="bb1f1-106">[in] Объект `ULONG32` указывает размер `locals` массива.</span><span class="sxs-lookup"><span data-stu-id="bb1f1-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="bb1f1-107">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для хранения локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="bb1f1-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="bb1f1-108">[out] Массив, получающий локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="bb1f1-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb1f1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb1f1-109">Return Value</span></span>  
 <span data-ttu-id="bb1f1-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="bb1f1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb1f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bb1f1-111">Requirements</span></span>  
 <span data-ttu-id="bb1f1-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bb1f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bb1f1-113">See Also</span></span>  
 [<span data-ttu-id="bb1f1-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="bb1f1-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
