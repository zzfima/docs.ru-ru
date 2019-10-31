---
title: Метод ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: 43408486fec9cd50222eed08ec2d3397bc11bc18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134624"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="a49e0-102">Метод ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a49e0-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="a49e0-103">Возвращает указанное число экземпляров [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a49e0-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a49e0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a49e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a49e0-105">Parameters</span></span>  
 <span data-ttu-id="a49e0-106">celt</span><span class="sxs-lookup"><span data-stu-id="a49e0-106">celt</span></span>  
 <span data-ttu-id="a49e0-107">окне Число извлекаемых корневых элементов.</span><span class="sxs-lookup"><span data-stu-id="a49e0-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="a49e0-108">корня</span><span class="sxs-lookup"><span data-stu-id="a49e0-108">roots</span></span>  
 <span data-ttu-id="a49e0-109">заполняет Массив указателей, каждый из которых указывает на объект [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) , представляющий корень объекта, который должен быть собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a49e0-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="a49e0-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="a49e0-110">pceltFetched</span></span>  
 <span data-ttu-id="a49e0-111">заполняет Указатель на число объектов [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) , фактически возвращаемых в `roots`.</span><span class="sxs-lookup"><span data-stu-id="a49e0-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="a49e0-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="a49e0-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a49e0-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="a49e0-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a49e0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a49e0-114">Requirements</span></span>  
 <span data-ttu-id="a49e0-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a49e0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a49e0-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a49e0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a49e0-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a49e0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a49e0-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a49e0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49e0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a49e0-119">See also</span></span>

- [<span data-ttu-id="a49e0-120">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a49e0-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="a49e0-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a49e0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
