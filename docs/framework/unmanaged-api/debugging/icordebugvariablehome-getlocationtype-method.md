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
ms.openlocfilehash: c04fa944f2a3da9b6548ada36443d5dda4725f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421133"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="e572f-102">Метод ICorDebugVariableHome::GetLocationType</span><span class="sxs-lookup"><span data-stu-id="e572f-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="e572f-103">Возвращает тип собственного расположение переменной.</span><span class="sxs-lookup"><span data-stu-id="e572f-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e572f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e572f-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e572f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e572f-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="e572f-106">[out] Указатель на тип переменной, в машинном коде места.</span><span class="sxs-lookup"><span data-stu-id="e572f-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="e572f-107">В разделе [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) перечисления для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="e572f-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e572f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e572f-108">Requirements</span></span>  
 <span data-ttu-id="e572f-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e572f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e572f-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e572f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e572f-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e572f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e572f-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e572f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e572f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e572f-113">See Also</span></span>  
 [<span data-ttu-id="e572f-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e572f-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="e572f-115">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="e572f-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
