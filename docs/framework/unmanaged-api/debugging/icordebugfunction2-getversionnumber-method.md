---
title: Метод ICorDebugFunction2::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc9c2af62184c83857b82445941f6087a05c2c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497175"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="3fe21-102">Метод ICorDebugFunction2::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="3fe21-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="3fe21-103">Получает версию "Изменить и продолжить" этой функции.</span><span class="sxs-lookup"><span data-stu-id="3fe21-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fe21-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fe21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fe21-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="3fe21-106">[out] Указатель на целое число, — это номер версии, представленный этим объектом ICorDebugFunction2 функции.</span><span class="sxs-lookup"><span data-stu-id="3fe21-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fe21-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fe21-107">Remarks</span></span>  
 <span data-ttu-id="3fe21-108">Среда выполнения отслеживает этой информации на количестве изменений, произошедших в каждый модуль во время сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="3fe21-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="3fe21-109">Номер версии функции входит более количества редактирования, которая представлена функция.</span><span class="sxs-lookup"><span data-stu-id="3fe21-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="3fe21-110">Исходная версия функции — версии 1.</span><span class="sxs-lookup"><span data-stu-id="3fe21-110">The function's original version is version 1.</span></span> <span data-ttu-id="3fe21-111">Номер увеличивается для модуля, каждый раз [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) вызывается для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="3fe21-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="3fe21-112">Таким образом Если тело функции был заменен в первый и третий вызов `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` может возвращать версии 1, 2 или 4 для этой функции, но не в версии 3.</span><span class="sxs-lookup"><span data-stu-id="3fe21-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="3fe21-113">(Эта функция будет иметь нет версии 3.)</span><span class="sxs-lookup"><span data-stu-id="3fe21-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="3fe21-114">Номер версии отслеживается отдельно для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="3fe21-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="3fe21-115">Таким образом при выполнении четырех изменений в 1 модуль и модуль 2 следующее изменение на модуле 1 присвоит номер версии 6 ко всем функциям, измененный в 1 модуль.</span><span class="sxs-lookup"><span data-stu-id="3fe21-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="3fe21-116">Если данное изменение затрагивает 2 модуля, функции в модуле 2 Получите номер версии 2.</span><span class="sxs-lookup"><span data-stu-id="3fe21-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="3fe21-117">Получить номер версии, `GetVersionNumber` метод может быть ниже, чем у полученных [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="3fe21-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="3fe21-118">[ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) метод выполняет те же функции, как `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="3fe21-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe21-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3fe21-119">Requirements</span></span>  
 <span data-ttu-id="3fe21-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fe21-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe21-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fe21-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fe21-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fe21-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fe21-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe21-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
