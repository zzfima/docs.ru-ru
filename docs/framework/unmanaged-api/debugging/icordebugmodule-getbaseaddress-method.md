---
title: Метод ICorDebugModule::GetBaseAddress
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ed6344f9a37d246a551699c94046b8c2b473fd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762691"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="6131d-102">Метод ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="6131d-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="6131d-103">Получает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="6131d-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6131d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6131d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6131d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6131d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="6131d-106">[out] Объект `CORDB_ADDRESS` , задающий базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="6131d-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6131d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6131d-107">Remarks</span></span>  
 <span data-ttu-id="6131d-108">Если модуль является собственным изображения (то есть, если модуль был создан генератором образов в машинном коде, NGen.exe), его базовый адрес будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="6131d-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6131d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6131d-109">Requirements</span></span>  
 <span data-ttu-id="6131d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6131d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6131d-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6131d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6131d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6131d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6131d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6131d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6131d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6131d-114">See also</span></span>
