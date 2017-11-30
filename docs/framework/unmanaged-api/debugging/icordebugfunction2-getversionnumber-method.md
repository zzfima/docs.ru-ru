---
title: "Метод ICorDebugFunction2::GetVersionNumber"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37b9e34174d88be08c92c54906ebd20977dc266a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="b7690-102">Метод ICorDebugFunction2::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="b7690-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="b7690-103">Возвращает версию этой функции изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="b7690-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7690-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7690-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7690-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7690-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="b7690-106">[out] Указатель на целое число, номер версии, представленного этим объектом ICorDebugFunction2 функции.</span><span class="sxs-lookup"><span data-stu-id="b7690-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7690-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7690-107">Remarks</span></span>  
 <span data-ttu-id="b7690-108">Среда выполнения хранит информацию о количестве изменений, произошедших в каждый модуль во время сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="b7690-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="b7690-109">Номер версии функции — одно больше числа редактирования, которая представлена функция.</span><span class="sxs-lookup"><span data-stu-id="b7690-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="b7690-110">Исходную версию функции — версия 1.</span><span class="sxs-lookup"><span data-stu-id="b7690-110">The function's original version is version 1.</span></span> <span data-ttu-id="b7690-111">Номер увеличивается для модуля каждый раз [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) вызывается для данного модуля.</span><span class="sxs-lookup"><span data-stu-id="b7690-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="b7690-112">Таким образом Если тело функции был заменен в первый и третий вызов `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` может вернуть 1, 2 или 4 для этой функции, но не версию 3.</span><span class="sxs-lookup"><span data-stu-id="b7690-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="b7690-113">(Эта функция будет иметь версии 3 не).</span><span class="sxs-lookup"><span data-stu-id="b7690-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="b7690-114">Номер версии отслеживается отдельно для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="b7690-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="b7690-115">Таким образом при выполнении четырех изменений на модуле 1 и модуль 2 следующее изменение на модуле 1 присвоит номер версии 6 всем измененным функциям в модуле 1.</span><span class="sxs-lookup"><span data-stu-id="b7690-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="b7690-116">Если данное изменение затрагивает модуль 2, функции модуля 2 получает номер версии 2.</span><span class="sxs-lookup"><span data-stu-id="b7690-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="b7690-117">Номер версии, получаемой в результате `GetVersionNumber` метод может быть ниже, чем у полученных [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7690-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="b7690-118">[ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) метод выполняет те же функции, как `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="b7690-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7690-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b7690-119">Requirements</span></span>  
 <span data-ttu-id="b7690-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7690-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7690-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7690-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7690-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7690-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7690-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7690-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
