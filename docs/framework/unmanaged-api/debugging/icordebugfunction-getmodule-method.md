---
title: Метод ICorDebugFunction::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6bfde8a934da857e580c603bd1c0115a04a4070
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754630"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="80fbe-102">Метод ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="80fbe-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="80fbe-103">Возвращает модуль, в котором определена эта функция.</span><span class="sxs-lookup"><span data-stu-id="80fbe-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fbe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80fbe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80fbe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80fbe-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="80fbe-106">[out] Указатель на адрес ICorDebugModule объект, представляющий модуль, в котором определена эта функция.</span><span class="sxs-lookup"><span data-stu-id="80fbe-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fbe-107">Требования</span><span class="sxs-lookup"><span data-stu-id="80fbe-107">Requirements</span></span>  
 <span data-ttu-id="80fbe-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80fbe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fbe-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80fbe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80fbe-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80fbe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80fbe-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80fbe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
