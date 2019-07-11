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
ms.openlocfilehash: f4b3b80546095b79dc5b551a9c5e92ec15c0dddb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771786"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="92ac9-102">Метод ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="92ac9-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="92ac9-103">Получает регистр, который содержит переменную с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="92ac9-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ac9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92ac9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ac9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92ac9-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="92ac9-106">[out] CorDebugRegister значение перечисления, указывающее регистра для переменной с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="92ac9-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92ac9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="92ac9-107">Return Value</span></span>  
 <span data-ttu-id="92ac9-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="92ac9-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="92ac9-109">Значение</span><span class="sxs-lookup"><span data-stu-id="92ac9-109">Value</span></span>|<span data-ttu-id="92ac9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="92ac9-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="92ac9-111">Переменная находится в регистре, обозначается `pRegister` аргумент.</span><span class="sxs-lookup"><span data-stu-id="92ac9-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="92ac9-112">Переменная не в регистр или в папку, зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="92ac9-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92ac9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="92ac9-113">Requirements</span></span>  
 <span data-ttu-id="92ac9-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92ac9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ac9-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ac9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ac9-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ac9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ac9-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ac9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ac9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="92ac9-118">See also</span></span>

- [<span data-ttu-id="92ac9-119">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="92ac9-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="92ac9-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="92ac9-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
