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
ms.openlocfilehash: 4ac1fc0b3567c49dfb36d2886926bee72d62a8dd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446067"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="f686d-102">Метод ISymUnmanagedVariable::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="f686d-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="f686d-103">Возвращает конечное смещение данной переменной в родительском объекте.</span><span class="sxs-lookup"><span data-stu-id="f686d-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="f686d-104">Если это локальная переменная в области, то конечное смещение будет находиться в пределах смещений, определенных для области.</span><span class="sxs-lookup"><span data-stu-id="f686d-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f686d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f686d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f686d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f686d-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f686d-107">заполняет Указатель на `ULONG32`, который получает конечное смещение.</span><span class="sxs-lookup"><span data-stu-id="f686d-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f686d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f686d-108">Return Value</span></span>  
 <span data-ttu-id="f686d-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f686d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f686d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f686d-110">Requirements</span></span>  
 <span data-ttu-id="f686d-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f686d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f686d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="f686d-112">See also</span></span>

- [<span data-ttu-id="f686d-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="f686d-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="f686d-114">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="f686d-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
