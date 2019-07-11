---
title: Метод ICorDebugVariableHome::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c0cae29cceb3f23c7d09cf096937c99641d5a87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773602"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="3614e-102">Метод ICorDebugVariableHome::GetCode</span><span class="sxs-lookup"><span data-stu-id="3614e-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="3614e-103">Возвращает экземпляр «ICorDebugCode», содержащий этот [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="3614e-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3614e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3614e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3614e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3614e-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="3614e-106">[out] Указатель на адрес экземпляра «ICorDebugCode», содержащий этот [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="3614e-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3614e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3614e-107">Requirements</span></span>  
 <span data-ttu-id="3614e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3614e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3614e-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3614e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3614e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3614e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3614e-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3614e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3614e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3614e-112">See also</span></span>

- [<span data-ttu-id="3614e-113">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="3614e-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
