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
ms.openlocfilehash: 9f334b4a28b0573fa938c2fda340c0c03175ff18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756876"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="2e829-102">Метод ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="2e829-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="2e829-103">Возвращает заданное число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) экземпляров, которые сопоставляют идентификаторов GUID, чтобы сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="2e829-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e829-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e829-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e829-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e829-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2e829-106">[in] Число получаемых объектов сопоставления типа GUID.</span><span class="sxs-lookup"><span data-stu-id="2e829-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="2e829-107">[out] Массив указателей, каждый из которых указывает [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) объект, сопоставляемый соответствующего объекта ICorDebugType GUID среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="2e829-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2e829-108">[out] Указатель на число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) объектов, фактически возвращенных в `values`.</span><span class="sxs-lookup"><span data-stu-id="2e829-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e829-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e829-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e829-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2e829-110">Requirements</span></span>  
 <span data-ttu-id="2e829-111">**Платформы:** Среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="2e829-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="2e829-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e829-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e829-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e829-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e829-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e829-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e829-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2e829-115">See also</span></span>

- [<span data-ttu-id="2e829-116">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="2e829-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="2e829-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2e829-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
