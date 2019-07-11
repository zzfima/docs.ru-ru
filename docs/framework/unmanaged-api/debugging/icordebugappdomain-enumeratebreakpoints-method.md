---
title: Метод ICorDebugAppDomain::EnumerateBreakpoints
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a683f1531ed28fbd8ef085414bb7cb365762ffde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738040"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="eef52-102">Метод ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="eef52-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="eef52-103">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="eef52-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eef52-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eef52-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eef52-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="eef52-106">[out] Указатель на адрес объекта ICorDebugBreakpointEnum, который является перечислителем для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="eef52-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eef52-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="eef52-107">Remarks</span></span>  
 <span data-ttu-id="eef52-108">Перечислитель включает все типы точек останова, включая точки останова функции и точки останова по данным.</span><span class="sxs-lookup"><span data-stu-id="eef52-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef52-109">Требования</span><span class="sxs-lookup"><span data-stu-id="eef52-109">Requirements</span></span>  
 <span data-ttu-id="eef52-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eef52-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef52-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eef52-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eef52-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eef52-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eef52-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
