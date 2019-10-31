---
title: Метод ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137818"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="6d79c-102">Метод ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="6d79c-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="6d79c-103">Возвращает значение, указывающее, помечается ли функция, представленная этим объектом ICorDebugFunction2, как пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="6d79c-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d79c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d79c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d79c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d79c-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="6d79c-106">заполняет Указатель на логическое значение, которое `true`, если эта функция помечена как пользовательский код; в противном случае значение равно `false`.</span><span class="sxs-lookup"><span data-stu-id="6d79c-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d79c-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6d79c-107">Remarks</span></span>  
 <span data-ttu-id="6d79c-108">Если функция, представленная этим `ICorDebugFunction2`, не может быть отлажена, `pbIsJustMyCode` всегда будет `false`.</span><span class="sxs-lookup"><span data-stu-id="6d79c-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d79c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6d79c-109">Requirements</span></span>  
 <span data-ttu-id="6d79c-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d79c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d79c-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d79c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d79c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d79c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d79c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d79c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
