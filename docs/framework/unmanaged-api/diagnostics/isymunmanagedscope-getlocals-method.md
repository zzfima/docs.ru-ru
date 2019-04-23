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
ms.openlocfilehash: 625609d8632f1f73ee2ec01e3b2e0e1af7e4a134
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085718"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="5a928-102">Метод ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="5a928-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="5a928-103">Возвращает локальные переменные, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="5a928-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a928-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a928-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a928-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a928-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="5a928-106">[in] Объект `ULONG32` указывает размер `locals` массива.</span><span class="sxs-lookup"><span data-stu-id="5a928-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="5a928-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для хранения локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="5a928-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="5a928-108">[out] Массив, получающий локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="5a928-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a928-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a928-109">Return Value</span></span>  
 <span data-ttu-id="5a928-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="5a928-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a928-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5a928-111">Requirements</span></span>  
 <span data-ttu-id="5a928-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5a928-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a928-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5a928-113">See also</span></span>

- [<span data-ttu-id="5a928-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="5a928-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
