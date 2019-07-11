---
title: Метод ICorDebugAppDomain::EnumerateSteppers
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea2c72a91aaa09d1c2d0e0944b73beb9ea313d0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738025"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="ee42a-102">Метод ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="ee42a-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="ee42a-103">Возвращает перечислитель для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="ee42a-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee42a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee42a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee42a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee42a-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="ee42a-106">[out] Указатель на адрес объекта ICorDebugStepperEnum, который является перечислителем для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="ee42a-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee42a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ee42a-107">Requirements</span></span>  
 <span data-ttu-id="ee42a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee42a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee42a-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee42a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee42a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee42a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee42a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee42a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
