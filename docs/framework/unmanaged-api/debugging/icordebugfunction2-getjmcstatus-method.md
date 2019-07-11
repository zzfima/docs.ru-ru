---
title: Метод ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2364c7c47aed1430a86aeee3daabf6b94cbf3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754479"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="297e8-102">Метод ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="297e8-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="297e8-103">Получает значение, указывающее, отмечена ли функция, представляемая этим объектом ICorDebugFunction2 как пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="297e8-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="297e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="297e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="297e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="297e8-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="297e8-106">[out] Указатель на логическое значение, которое является `true`, если эта функция помечается как код пользователя; в противном случае значение равно `false`.</span><span class="sxs-lookup"><span data-stu-id="297e8-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="297e8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="297e8-107">Remarks</span></span>  
 <span data-ttu-id="297e8-108">Если функция, представленный данным `ICorDebugFunction2` невозможна, `pbIsJustMyCode` всегда будет `false`.</span><span class="sxs-lookup"><span data-stu-id="297e8-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="297e8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="297e8-109">Requirements</span></span>  
 <span data-ttu-id="297e8-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="297e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="297e8-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="297e8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="297e8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="297e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="297e8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="297e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
