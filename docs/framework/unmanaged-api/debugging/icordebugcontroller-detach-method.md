---
title: Метод ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f2dae147f8667a73036dbcf873e2082996b2755
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666989"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="9a490-102">Метод ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="9a490-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="9a490-103">Отключает отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9a490-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a490-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a490-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9a490-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a490-105">Remarks</span></span>  
 <span data-ttu-id="9a490-106">Процесса или домена приложения продолжит выполнение, как правило, но объект «ICorDebugProcess» или «ICorDebugAppDomain» больше не является допустимым и обратные вызовы не произойдет.</span><span class="sxs-lookup"><span data-stu-id="9a490-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="9a490-107">В .NET Framework версии 2.0 Если включена отладка неуправляемого кода, этот метод завершится ошибкой из-за ограничений операционных систем.</span><span class="sxs-lookup"><span data-stu-id="9a490-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a490-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9a490-108">Requirements</span></span>  
 <span data-ttu-id="9a490-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a490-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a490-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a490-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a490-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a490-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a490-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a490-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a490-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9a490-113">See also</span></span>

