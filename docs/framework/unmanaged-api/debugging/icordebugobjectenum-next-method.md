---
title: Метод ICorDebugObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: adcfbf1207ad7895ab55f7e5cf9581905cb826bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096108"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="a8a69-102">Метод ICorDebugObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a8a69-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="a8a69-103">Возвращает относительные виртуальные адреса (RVA) указанного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="a8a69-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8a69-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8a69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8a69-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a8a69-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="a8a69-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="a8a69-107">заполняет Массив указателей, каждый из которых указывает на объект CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="a8a69-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a8a69-108">заполняет Указатель на число фактически возвращенных объектов.</span><span class="sxs-lookup"><span data-stu-id="a8a69-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="a8a69-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="a8a69-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8a69-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a8a69-110">Requirements</span></span>  
 <span data-ttu-id="a8a69-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8a69-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8a69-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8a69-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8a69-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8a69-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8a69-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8a69-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a69-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a8a69-115">See also</span></span>
