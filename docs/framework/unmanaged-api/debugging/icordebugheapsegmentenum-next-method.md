---
title: Метод ICorDebugHeapSegmentEnum::Next
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 8a267ec7123edb73ad51f0781a78344119ec6f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178898"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="c3434-102">Метод ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c3434-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="c3434-103">Получает указанное количество [COR_HEAPOBJECT](cor-heapobject-structure.md) экземпляров, содержащих информацию о регионах памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="c3434-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3434-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3434-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3434-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3434-105">Parameters</span></span>  
 <span data-ttu-id="c3434-106">celt</span><span class="sxs-lookup"><span data-stu-id="c3434-106">celt</span></span>  
 <span data-ttu-id="c3434-107">(в) Количество сегментов, которые необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="c3434-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="c3434-108">сегменты</span><span class="sxs-lookup"><span data-stu-id="c3434-108">segments</span></span>  
 <span data-ttu-id="c3434-109">(ваут) Массив указателей, каждый из которых указывает на [COR_HEAPOBJECT](cor-heapobject-structure.md) объект, предоставляющий информацию о области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="c3434-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="c3434-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="c3434-110">pceltFetched</span></span>  
 <span data-ttu-id="c3434-111">(ваут) Указатель на количество [COR_HEAPOBJECT](cor-heapobject-structure.md) объектов `segments`фактически вернулся в .</span><span class="sxs-lookup"><span data-stu-id="c3434-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="c3434-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="c3434-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3434-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3434-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3434-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c3434-114">Requirements</span></span>  
 <span data-ttu-id="c3434-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3434-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3434-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3434-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3434-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3434-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3434-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3434-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3434-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c3434-119">See also</span></span>

- [<span data-ttu-id="c3434-120">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="c3434-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="c3434-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c3434-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
