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
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996272"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="f8b9b-102">Метод ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="f8b9b-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="f8b9b-103">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f8b9b-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8b9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8b9b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8b9b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8b9b-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="f8b9b-106">[out] Указатель на адрес объекта ICorDebugBreakpointEnum, который является перечислителем для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f8b9b-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8b9b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8b9b-107">Remarks</span></span>  
 <span data-ttu-id="f8b9b-108">Перечислитель включает все типы точек останова, включая точки останова функции и точки останова по данным.</span><span class="sxs-lookup"><span data-stu-id="f8b9b-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8b9b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f8b9b-109">Requirements</span></span>  
 <span data-ttu-id="f8b9b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8b9b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8b9b-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8b9b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8b9b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8b9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8b9b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8b9b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
