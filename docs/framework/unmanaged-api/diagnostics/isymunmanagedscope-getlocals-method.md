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
ms.openlocfilehash: d6c48a7ae62155dc558fb4a62b3e2573bea77594
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499177"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="78e99-102">Метод ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="78e99-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="78e99-103">Возвращает локальные переменные, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="78e99-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78e99-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78e99-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78e99-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78e99-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="78e99-106">[in] Объект `ULONG32` указывает размер `locals` массива.</span><span class="sxs-lookup"><span data-stu-id="78e99-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="78e99-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для хранения локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="78e99-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="78e99-108">[out] Массив, получающий локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="78e99-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78e99-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="78e99-109">Return Value</span></span>  
 <span data-ttu-id="78e99-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="78e99-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78e99-111">Требования</span><span class="sxs-lookup"><span data-stu-id="78e99-111">Requirements</span></span>  
 <span data-ttu-id="78e99-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="78e99-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e99-113">См. также</span><span class="sxs-lookup"><span data-stu-id="78e99-113">See also</span></span>
- [<span data-ttu-id="78e99-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="78e99-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
