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
ms.openlocfilehash: 8c0fa19841580c7cfe8902577c3f756712a35893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420664"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="87ea8-102">Метод ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="87ea8-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="87ea8-103">Возвращает адрес объекта «ICorDebugValue», который находится в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="87ea8-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87ea8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87ea8-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87ea8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87ea8-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="87ea8-106">[out] Указатель на `CORDB_ADDRESS` объект, указывающий адрес, этот объект значения.</span><span class="sxs-lookup"><span data-stu-id="87ea8-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87ea8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="87ea8-107">Remarks</span></span>  
 <span data-ttu-id="87ea8-108">Если значение недоступно, возвращается 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="87ea8-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="87ea8-109">Это может произойти, если значение хотя бы частично находится в регистрах или хранится в дескрипторе сборщика мусора (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="87ea8-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87ea8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="87ea8-110">Requirements</span></span>  
 <span data-ttu-id="87ea8-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87ea8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87ea8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87ea8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87ea8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87ea8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87ea8-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87ea8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ea8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="87ea8-115">See Also</span></span>  
 
