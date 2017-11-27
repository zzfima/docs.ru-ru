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
ms.openlocfilehash: 5e58059bbd3e9bf8d3db80d36e84e1f4496eb0bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="3f1b4-102">Метод ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="3f1b4-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="3f1b4-103">Возвращает перечислитель для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="3f1b4-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f1b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f1b4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f1b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f1b4-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="3f1b4-106">[out] Указатель на адрес объекта ICorDebugStepperEnum, который является перечислителем для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="3f1b4-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f1b4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3f1b4-107">Requirements</span></span>  
 <span data-ttu-id="3f1b4-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f1b4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f1b4-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f1b4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f1b4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f1b4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f1b4-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f1b4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
