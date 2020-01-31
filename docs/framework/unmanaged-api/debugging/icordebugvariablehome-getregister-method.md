---
title: 'Метод ICorDebugVariableHome::'
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
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790979"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="a82b3-102">Метод ICorDebugVariableHome::</span><span class="sxs-lookup"><span data-stu-id="a82b3-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="a82b3-103">Возвращает регистр, содержащий переменную с типом расположения `VLT_REGISTER`и базовый регистр для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="a82b3-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a82b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a82b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a82b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a82b3-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="a82b3-106">заполняет Значение перечисления CorDebugRegister, указывающее регистр для переменной с типом расположения `VLT_REGISTER`, а также базовый регистр для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="a82b3-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a82b3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a82b3-107">Return Value</span></span>  
 <span data-ttu-id="a82b3-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a82b3-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="a82b3-109">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="a82b3-109">Value</span></span>|<span data-ttu-id="a82b3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a82b3-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="a82b3-111">Переменная находится в регистре, указанном аргументом `pRegister`.</span><span class="sxs-lookup"><span data-stu-id="a82b3-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="a82b3-112">Переменная не находится в регистре или расположении, относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="a82b3-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a82b3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a82b3-113">Requirements</span></span>  
 <span data-ttu-id="a82b3-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a82b3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82b3-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a82b3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a82b3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a82b3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a82b3-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a82b3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82b3-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="a82b3-118">See also</span></span>

- [<span data-ttu-id="a82b3-119">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="a82b3-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="a82b3-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a82b3-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
