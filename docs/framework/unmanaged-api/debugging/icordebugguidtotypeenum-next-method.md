---
title: Метод ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f48c142b2b3742d01a8f796f11d5c9174529a041
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105830"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="04bb6-102">Метод ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="04bb6-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="04bb6-103">Возвращает заданное число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) экземпляров, которые сопоставляют идентификаторов GUID, чтобы сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="04bb6-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04bb6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04bb6-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04bb6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04bb6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="04bb6-106">[in] Число получаемых объектов сопоставления типа GUID.</span><span class="sxs-lookup"><span data-stu-id="04bb6-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="04bb6-107">[out] Массив указателей, каждый из которых указывает [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) объекта, сопоставляющего [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID для соответствующего объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="04bb6-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="04bb6-108">[out] Указатель на число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) объектов, фактически возвращенных в `values`.</span><span class="sxs-lookup"><span data-stu-id="04bb6-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04bb6-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="04bb6-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04bb6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="04bb6-110">Requirements</span></span>  
 **<span data-ttu-id="04bb6-111">Платформы:</span><span class="sxs-lookup"><span data-stu-id="04bb6-111">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="04bb6-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04bb6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04bb6-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04bb6-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="04bb6-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="04bb6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04bb6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="04bb6-115">See also</span></span>

- [<span data-ttu-id="04bb6-116">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="04bb6-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="04bb6-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="04bb6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
