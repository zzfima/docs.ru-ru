---
title: Метод ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f34a2fe2bb1f92e75f77c086b03776ec59495600
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995752"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="0dca1-102">Метод ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="0dca1-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="0dca1-103">Получает экземпляр ICorDebugCode, представляющее код промежуточного языка MSIL Microsoft, связанного с данным объектом ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="0dca1-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dca1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dca1-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dca1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0dca1-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="0dca1-106">[out] Указатель на `ICorDebugCode` экземпляра, или значение null, если функция не была скомпилирована в MSIL.</span><span class="sxs-lookup"><span data-stu-id="0dca1-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dca1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0dca1-107">Remarks</span></span>  
 <span data-ttu-id="0dca1-108">Если изменить и продолжить была разрешена в этой функции `GetILCode` метод получит код MSIL, соответствующий этой функции измененная версия кода в системе common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0dca1-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dca1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0dca1-109">Requirements</span></span>  
 <span data-ttu-id="0dca1-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dca1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dca1-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dca1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dca1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dca1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dca1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dca1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
