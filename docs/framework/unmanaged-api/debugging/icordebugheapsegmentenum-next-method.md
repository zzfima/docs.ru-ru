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
ms.openlocfilehash: 89ce4eafa46be3e9ba7cdb06884034a521e43bca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777538"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="b77ad-102">Метод ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b77ad-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="b77ad-103">Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения о регионах памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="b77ad-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b77ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b77ad-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b77ad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b77ad-105">Parameters</span></span>  
 <span data-ttu-id="b77ad-106">celt</span><span class="sxs-lookup"><span data-stu-id="b77ad-106">celt</span></span>  
 <span data-ttu-id="b77ad-107">окне Число извлекаемых сегментов.</span><span class="sxs-lookup"><span data-stu-id="b77ad-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="b77ad-108">сегменты</span><span class="sxs-lookup"><span data-stu-id="b77ad-108">segments</span></span>  
 <span data-ttu-id="b77ad-109">заполняет Массив указателей, каждый из которых указывает на объект [COR_HEAPOBJECT](cor-heapobject-structure.md) , который предоставляет сведения о области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="b77ad-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="b77ad-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b77ad-110">pceltFetched</span></span>  
 <span data-ttu-id="b77ad-111">заполняет Указатель на число объектов [COR_HEAPOBJECT](cor-heapobject-structure.md) , фактически возвращаемых в `segments`.</span><span class="sxs-lookup"><span data-stu-id="b77ad-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="b77ad-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="b77ad-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b77ad-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="b77ad-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b77ad-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b77ad-114">Requirements</span></span>  
 <span data-ttu-id="b77ad-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b77ad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b77ad-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b77ad-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b77ad-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b77ad-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b77ad-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b77ad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77ad-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="b77ad-119">See also</span></span>

- [<span data-ttu-id="b77ad-120">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="b77ad-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="b77ad-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b77ad-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
