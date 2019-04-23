---
title: Метод ISymUnmanagedVariable::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a30dff869075a201a669d1e703bc003b011fc3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196285"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="14ba0-102">Метод ISymUnmanagedVariable::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="14ba0-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="14ba0-103">Возвращает начальное смещение переменной внутри родительского.</span><span class="sxs-lookup"><span data-stu-id="14ba0-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="14ba0-104">Если это локальной переменной в области, начальное смещение выходит в границах смещений, определенных для данной области.</span><span class="sxs-lookup"><span data-stu-id="14ba0-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14ba0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14ba0-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14ba0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="14ba0-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="14ba0-107">[out] Указатель на `ULONG32` , который получает начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="14ba0-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14ba0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14ba0-108">Return Value</span></span>  
 <span data-ttu-id="14ba0-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="14ba0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14ba0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="14ba0-110">Requirements</span></span>  
 <span data-ttu-id="14ba0-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="14ba0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ba0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="14ba0-112">See also</span></span>

- [<span data-ttu-id="14ba0-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="14ba0-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="14ba0-114">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="14ba0-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
