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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15b102be5a792f982edeb320199576bdddbd859a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412364"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="82f07-102">Метод ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="82f07-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="82f07-103">Обозначает функцию, представленную в этом ICorDebugFunction2 только мой код пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="82f07-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82f07-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82f07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="82f07-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="82f07-106">[in] Значение `true` пометить ее как код пользователя; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="82f07-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="82f07-107">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="82f07-107">Return Values</span></span>  
  
|<span data-ttu-id="82f07-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82f07-108">HRESULT</span></span>|<span data-ttu-id="82f07-109">Описание</span><span class="sxs-lookup"><span data-stu-id="82f07-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="82f07-110">Функция была успешно отмечена.</span><span class="sxs-lookup"><span data-stu-id="82f07-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="82f07-111">Функция не может быть помечена как код пользователя, так как он не может быть отлажен.</span><span class="sxs-lookup"><span data-stu-id="82f07-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82f07-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="82f07-112">Remarks</span></span>  
 <span data-ttu-id="82f07-113">Пошаговым только мой код будет пропускать код, не написанный пользователем.</span><span class="sxs-lookup"><span data-stu-id="82f07-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="82f07-114">Пользовательский код должен быть подмножеством отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="82f07-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f07-115">Требования</span><span class="sxs-lookup"><span data-stu-id="82f07-115">Requirements</span></span>  
 <span data-ttu-id="82f07-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82f07-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f07-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82f07-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82f07-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82f07-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82f07-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f07-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
