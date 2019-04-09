---
title: Метод ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac550ee7b1d66612557b30d15c275c90cf09b8af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187354"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="98e8e-102">Метод ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="98e8e-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="98e8e-103">Возвращает адрес объекта «ICorDebugValue», который находится в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="98e8e-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98e8e-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98e8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98e8e-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="98e8e-106">[out] Указатель на `CORDB_ADDRESS` , указывающий адрес этого объекта значение.</span><span class="sxs-lookup"><span data-stu-id="98e8e-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98e8e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="98e8e-107">Remarks</span></span>  
 <span data-ttu-id="98e8e-108">Если значение недоступно, возвращается 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="98e8e-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="98e8e-109">Это может произойти, если значение хотя бы частично в регистрах или хранится в дескрипторе сборщика мусора (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="98e8e-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e8e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="98e8e-110">Requirements</span></span>  
 <span data-ttu-id="98e8e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98e8e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e8e-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98e8e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98e8e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98e8e-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="98e8e-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="98e8e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98e8e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="98e8e-115">See also</span></span>
