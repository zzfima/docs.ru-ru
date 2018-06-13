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
ms.openlocfilehash: 7bf3aa6d883dffece6ba89d41005499cc6206906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401295"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="52a07-102">Метод ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="52a07-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="52a07-103">Возвращает перечислитель для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="52a07-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52a07-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52a07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52a07-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="52a07-106">[out] Указатель на адрес объекта ICorDebugStepperEnum, который является перечислителем для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="52a07-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a07-107">Требования</span><span class="sxs-lookup"><span data-stu-id="52a07-107">Requirements</span></span>  
 <span data-ttu-id="52a07-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a07-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a07-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52a07-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52a07-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52a07-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52a07-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
