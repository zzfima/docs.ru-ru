---
title: "Метод ICorDebugAppDomain::EnumerateSteppers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.EnumerateSteppers
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b410eabee546307488449e577d9e102ac6a210b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="ceb3f-102">Метод ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="ceb3f-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="ceb3f-103">Возвращает перечислитель для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="ceb3f-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ceb3f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ceb3f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ceb3f-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="ceb3f-106">[out] Указатель на адрес объекта ICorDebugStepperEnum, который является перечислителем для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="ceb3f-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb3f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ceb3f-107">Requirements</span></span>  
 <span data-ttu-id="ceb3f-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb3f-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceb3f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceb3f-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceb3f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceb3f-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb3f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
