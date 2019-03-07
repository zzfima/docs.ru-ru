---
title: Метод ICorDebugFunction::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695ce7f25813a191c74bec6563fc7f8ae8d1143d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496122"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="5f82c-102">Метод ICorDebugFunction::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5f82c-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="5f82c-103">Создает точку останова в начале этой функции.</span><span class="sxs-lookup"><span data-stu-id="5f82c-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f82c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f82c-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f82c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f82c-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="5f82c-106">[out] Указатель на адрес ICorDebugFunctionBreakpoint объект, представляющий новую точку останова функции.</span><span class="sxs-lookup"><span data-stu-id="5f82c-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f82c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5f82c-107">Requirements</span></span>  
 <span data-ttu-id="5f82c-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f82c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f82c-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f82c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f82c-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f82c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f82c-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f82c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
