---
title: Метод ICorDebugVariableHome::GetLocationType
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba0387b84f8d32831b79dd6c361bcdbb78f8bbba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499503"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="926c3-102">Метод ICorDebugVariableHome::GetLocationType</span><span class="sxs-lookup"><span data-stu-id="926c3-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="926c3-103">Получает тип переменной собственному расположению.</span><span class="sxs-lookup"><span data-stu-id="926c3-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="926c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="926c3-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="926c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="926c3-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="926c3-106">[out] Указатель на тип переменной собственному расположению.</span><span class="sxs-lookup"><span data-stu-id="926c3-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="926c3-107">См. в разделе [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) перечисления Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="926c3-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="926c3-108">Требования</span><span class="sxs-lookup"><span data-stu-id="926c3-108">Requirements</span></span>  
 <span data-ttu-id="926c3-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="926c3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="926c3-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="926c3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="926c3-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="926c3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="926c3-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="926c3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926c3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="926c3-113">See also</span></span>
- [<span data-ttu-id="926c3-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="926c3-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="926c3-115">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="926c3-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
