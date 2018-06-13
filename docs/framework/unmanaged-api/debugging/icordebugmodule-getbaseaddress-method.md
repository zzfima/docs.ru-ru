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
ms.openlocfilehash: 10e7da7711cd63579589fda416d0d3a4f777eefe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412549"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="e7a61-102">Метод ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="e7a61-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="e7a61-103">Получает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="e7a61-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7a61-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7a61-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7a61-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="e7a61-106">[out] Объект `CORDB_ADDRESS` , задающий базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="e7a61-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7a61-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7a61-107">Remarks</span></span>  
 <span data-ttu-id="e7a61-108">Если модуль является собственного образа (то есть, если модуль был создан генератором образов в машинном коде NGen.exe), его базовый адрес должен быть равен нулю.</span><span class="sxs-lookup"><span data-stu-id="e7a61-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a61-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e7a61-109">Requirements</span></span>  
 <span data-ttu-id="e7a61-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7a61-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a61-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7a61-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7a61-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7a61-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7a61-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a61-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a61-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e7a61-114">See Also</span></span>  
    
 
