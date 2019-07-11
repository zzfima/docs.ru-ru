---
title: Метод ISymUnmanagedVariable::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ef32a963b73f2109b9747ef303e8ccd6a729838
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778262"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="cf48a-102">Метод ISymUnmanagedVariable::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="cf48a-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="cf48a-103">Возвращает конечное смещение переменной внутри родительского.</span><span class="sxs-lookup"><span data-stu-id="cf48a-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="cf48a-104">Если это локальной переменной в области, конечное смещение выходит в границах смещений, определенных для данной области.</span><span class="sxs-lookup"><span data-stu-id="cf48a-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf48a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf48a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf48a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf48a-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="cf48a-107">[out] Указатель на `ULONG32` , который получает конечное смещение.</span><span class="sxs-lookup"><span data-stu-id="cf48a-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf48a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cf48a-108">Return Value</span></span>  
 <span data-ttu-id="cf48a-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="cf48a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf48a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cf48a-110">Requirements</span></span>  
 <span data-ttu-id="cf48a-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cf48a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf48a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cf48a-112">See also</span></span>

- [<span data-ttu-id="cf48a-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="cf48a-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="cf48a-114">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="cf48a-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
