---
title: Метод ICorDebugCode::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 825840536968562a53d9e05b8a4628a1df79407d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700837"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="4ed3b-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="4ed3b-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="4ed3b-103">Возвращает "ICorDebugFunction", связанный с этим "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="4ed3b-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ed3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ed3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ed3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ed3b-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="4ed3b-106">заполняет Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="4ed3b-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ed3b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ed3b-107">Remarks</span></span>  
 <span data-ttu-id="4ed3b-108">`ICorDebugCode` и `ICorDebugFunction` поддерживают связь "один к одному".</span><span class="sxs-lookup"><span data-stu-id="4ed3b-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ed3b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4ed3b-109">Requirements</span></span>  
 <span data-ttu-id="4ed3b-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ed3b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ed3b-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4ed3b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ed3b-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="4ed3b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ed3b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ed3b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
