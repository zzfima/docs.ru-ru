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
ms.openlocfilehash: cfd7ee890a7f2c3ea8cd3de9fbe830575c0ca10c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402778"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="6c56f-102">Метод ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="6c56f-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="6c56f-103">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6c56f-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c56f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c56f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c56f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c56f-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="6c56f-106">[out] Указатель на адрес объекта ICorDebugBreakpointEnum, который является перечислителем для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6c56f-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c56f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c56f-107">Remarks</span></span>  
 <span data-ttu-id="6c56f-108">Перечислитель включает все типы точек останова, включая функции точки останова и точки останова в данных.</span><span class="sxs-lookup"><span data-stu-id="6c56f-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c56f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6c56f-109">Requirements</span></span>  
 <span data-ttu-id="6c56f-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c56f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c56f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c56f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c56f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c56f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c56f-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c56f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
