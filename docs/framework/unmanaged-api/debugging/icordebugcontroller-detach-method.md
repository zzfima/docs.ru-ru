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
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151805"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="36cc2-102">Метод ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="36cc2-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="36cc2-103">Отключает отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="36cc2-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36cc2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36cc2-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="36cc2-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="36cc2-105">Remarks</span></span>  
 <span data-ttu-id="36cc2-106">Процесса или домена приложения продолжит выполнение, как правило, но объект «ICorDebugProcess» или «ICorDebugAppDomain» больше не является допустимым и обратные вызовы не произойдет.</span><span class="sxs-lookup"><span data-stu-id="36cc2-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="36cc2-107">В .NET Framework версии 2.0 Если включена отладка неуправляемого кода, этот метод завершится ошибкой из-за ограничений операционных систем.</span><span class="sxs-lookup"><span data-stu-id="36cc2-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36cc2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="36cc2-108">Requirements</span></span>  
 <span data-ttu-id="36cc2-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36cc2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36cc2-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36cc2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36cc2-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36cc2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36cc2-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36cc2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36cc2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="36cc2-113">See also</span></span>
