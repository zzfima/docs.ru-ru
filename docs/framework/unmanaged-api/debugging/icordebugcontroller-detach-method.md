---
title: "Метод ICorDebugController::Detach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Detach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59fe2c4bfbd91afd263a0ada1eb355aaa8914aa2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="3ffac-102">Метод ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="3ffac-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="3ffac-103">Отсоединяет отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3ffac-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ffac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ffac-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3ffac-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ffac-105">Remarks</span></span>  
 <span data-ttu-id="3ffac-106">Процесс или домен приложения продолжает выполнение, как правило, но объект «ICorDebugProcess» или «ICorDebugAppDomain» больше не является допустимым и обратные вызовы не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="3ffac-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="3ffac-107">В .NET Framework версии 2.0 Если включена отладка неуправляемого кода этот метод завершается ошибкой из-за ограничений операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3ffac-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ffac-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3ffac-108">Requirements</span></span>  
 <span data-ttu-id="3ffac-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ffac-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ffac-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ffac-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ffac-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ffac-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ffac-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ffac-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ffac-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3ffac-113">See Also</span></span>  
 
