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
ms.openlocfilehash: 6e45f5411d48032b86403e35358d7ce83d5f97c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777912"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="bdd16-102">Метод ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="bdd16-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="bdd16-103">Возвращает локальные переменные, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="bdd16-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdd16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdd16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdd16-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="bdd16-106">[in] Объект `ULONG32` указывает размер `locals` массива.</span><span class="sxs-lookup"><span data-stu-id="bdd16-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="bdd16-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для хранения локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="bdd16-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="bdd16-108">[out] Массив, получающий локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="bdd16-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdd16-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bdd16-109">Return Value</span></span>  
 <span data-ttu-id="bdd16-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="bdd16-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdd16-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bdd16-111">Requirements</span></span>  
 <span data-ttu-id="bdd16-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bdd16-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd16-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bdd16-113">See also</span></span>

- [<span data-ttu-id="bdd16-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="bdd16-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
