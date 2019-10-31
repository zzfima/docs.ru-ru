---
title: Метод ICorDebugCode::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 217ca0a850926e5f697340cece264c6ed442a9bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125647"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="69fe3-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="69fe3-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="69fe3-103">Возвращает "ICorDebugFunction", связанный с этим "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="69fe3-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69fe3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69fe3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69fe3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69fe3-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="69fe3-106">заполняет Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="69fe3-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69fe3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="69fe3-107">Remarks</span></span>  
 <span data-ttu-id="69fe3-108">`ICorDebugCode` и `ICorDebugFunction` поддерживать связь "один к одному".</span><span class="sxs-lookup"><span data-stu-id="69fe3-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69fe3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="69fe3-109">Requirements</span></span>  
 <span data-ttu-id="69fe3-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69fe3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69fe3-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69fe3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69fe3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69fe3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69fe3-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69fe3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
