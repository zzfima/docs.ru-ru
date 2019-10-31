---
title: Метод ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: 758364b2d63343e464b727d5a1c1817533a6acea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137786"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="8b093-102">Метод ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="8b093-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="8b093-103">Помечает функцию, представленную этим ICorDebugFunction2, для Только мой код пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="8b093-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b093-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b093-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b093-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b093-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="8b093-106">окне Задайте значение `true`, чтобы пометить функцию как пользовательский код; в противном случае задайте значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8b093-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="8b093-107">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="8b093-107">Return Values</span></span>  
  
|<span data-ttu-id="8b093-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b093-108">HRESULT</span></span>|<span data-ttu-id="8b093-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8b093-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8b093-110">Функция была успешно помечена.</span><span class="sxs-lookup"><span data-stu-id="8b093-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="8b093-111">Функция не может быть помечена как пользовательский код, так как ее отладка невозможна.</span><span class="sxs-lookup"><span data-stu-id="8b093-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b093-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="8b093-112">Remarks</span></span>  
 <span data-ttu-id="8b093-113">Только мой код пошаговое средство пропускает код, не являющийся пользовательским.</span><span class="sxs-lookup"><span data-stu-id="8b093-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="8b093-114">Пользовательский код должен быть подмножеством отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="8b093-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b093-115">Требования</span><span class="sxs-lookup"><span data-stu-id="8b093-115">Requirements</span></span>  
 <span data-ttu-id="8b093-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b093-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b093-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b093-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b093-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b093-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b093-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b093-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
