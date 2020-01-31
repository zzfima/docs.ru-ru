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
ms.openlocfilehash: d85885d750f3c98e46b3e44418564da18850d3ec
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794489"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="9308f-102">Метод ICorDebugFunction2::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="9308f-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="9308f-103">Возвращает версию функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="9308f-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9308f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9308f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9308f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9308f-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="9308f-106">заполняет Указатель на целое число, представляющее номер версии функции, представленной этим объектом ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="9308f-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9308f-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="9308f-107">Remarks</span></span>  
 <span data-ttu-id="9308f-108">Среда выполнения отслеживает количество изменений, выполненных в каждом модуле во время сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="9308f-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="9308f-109">Номер версии функции — это значение, превышающее число изменений, введенных в функцию.</span><span class="sxs-lookup"><span data-stu-id="9308f-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="9308f-110">Исходной версией функции является версия 1.</span><span class="sxs-lookup"><span data-stu-id="9308f-110">The function's original version is version 1.</span></span> <span data-ttu-id="9308f-111">Число увеличивается для модуля каждый раз, когда для этого модуля вызывается [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9308f-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="9308f-112">Таким словами, если тело функции было заменено в первом и третьем вызове `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` может возвращать версию 1, 2 или 4 для этой функции, но не версию 3.</span><span class="sxs-lookup"><span data-stu-id="9308f-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="9308f-113">(Эта функция не имеет версии 3.)</span><span class="sxs-lookup"><span data-stu-id="9308f-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="9308f-114">Номер версии ведется отдельно для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="9308f-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="9308f-115">Поэтому при выполнении четырех изменений в модуле 1 и отсутствии в модуле 2 при следующем редактировании в модуле 1 будет присвоен номер версии 6 всем измененным функциям в модуле 1.</span><span class="sxs-lookup"><span data-stu-id="9308f-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="9308f-116">Если одно и то же изменение касается модуля 2, функции в модуле 2 будут получать номер версии 2.</span><span class="sxs-lookup"><span data-stu-id="9308f-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="9308f-117">Номер версии, полученный методом `GetVersionNumber`, может быть меньше, чем получает метод [ICorDebugFunction:: GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="9308f-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="9308f-118">Метод [ICorDebugCode:: жетверсионнумбер](icordebugcode-getversionnumber-method.md) выполняет ту же операцию, что и `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="9308f-118">The [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9308f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9308f-119">Requirements</span></span>  
 <span data-ttu-id="9308f-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9308f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9308f-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9308f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9308f-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9308f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9308f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9308f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
