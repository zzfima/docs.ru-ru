---
title: "Метод ICorDebugVariableHome::GetRegister"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54f1c737b0c6ce6281a71419cbd8c88277702f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="d67f7-102">Метод ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="d67f7-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="d67f7-103">Возвращает регистра, который содержит переменную с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="d67f7-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d67f7-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d67f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d67f7-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="d67f7-106">[out] CorDebugRegister значение перечисления, указывающее register для переменной с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="d67f7-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d67f7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d67f7-107">Return Value</span></span>  
 <span data-ttu-id="d67f7-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d67f7-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="d67f7-109">Значение</span><span class="sxs-lookup"><span data-stu-id="d67f7-109">Value</span></span>|<span data-ttu-id="d67f7-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="d67f7-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="d67f7-111">Переменная находится в регистре, обозначенном `pRegister` аргумент.</span><span class="sxs-lookup"><span data-stu-id="d67f7-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="d67f7-112">Переменная не находится в регистрах или расположение относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="d67f7-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d67f7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d67f7-113">Requirements</span></span>  
 <span data-ttu-id="d67f7-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d67f7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67f7-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d67f7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d67f7-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d67f7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d67f7-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67f7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67f7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d67f7-118">See Also</span></span>  
 [<span data-ttu-id="d67f7-119">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="d67f7-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="d67f7-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="d67f7-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
