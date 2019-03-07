---
title: Метод ICorDebugVariableHome::GetRegister
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73ab94765e1b76cb8521a0d546d6bc61384aad5f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480745"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="45a41-102">Метод ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="45a41-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="45a41-103">Получает регистр, который содержит переменную с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="45a41-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45a41-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45a41-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="45a41-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="45a41-106">[out] CorDebugRegister значение перечисления, указывающее регистра для переменной с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="45a41-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45a41-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="45a41-107">Return Value</span></span>  
 <span data-ttu-id="45a41-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="45a41-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="45a41-109">Значение</span><span class="sxs-lookup"><span data-stu-id="45a41-109">Value</span></span>|<span data-ttu-id="45a41-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="45a41-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="45a41-111">Переменная находится в регистре, обозначается `pRegister` аргумент.</span><span class="sxs-lookup"><span data-stu-id="45a41-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="45a41-112">Переменная не в регистр или в папку, зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="45a41-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45a41-113">Требования</span><span class="sxs-lookup"><span data-stu-id="45a41-113">Requirements</span></span>  
 <span data-ttu-id="45a41-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a41-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45a41-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45a41-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45a41-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45a41-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a41-118">См. также</span><span class="sxs-lookup"><span data-stu-id="45a41-118">See also</span></span>
- [<span data-ttu-id="45a41-119">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="45a41-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="45a41-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="45a41-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
