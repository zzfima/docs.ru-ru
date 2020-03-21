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
ms.openlocfilehash: d87f414e9dfd05a519b60efc7ecdd5328a6dd86f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178868"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="1c6f6-102">Метод ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="1c6f6-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="1c6f6-103">Получает указанное количество [COR_GC_REFERENCE](cor-gc-reference-structure.md) экземпляров, содержащих информацию об объектах, которые будут собраны мусором.</span><span class="sxs-lookup"><span data-stu-id="1c6f6-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c6f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c6f6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c6f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c6f6-105">Parameters</span></span>  
 <span data-ttu-id="1c6f6-106">celt</span><span class="sxs-lookup"><span data-stu-id="1c6f6-106">celt</span></span>  
 <span data-ttu-id="1c6f6-107">(в) Количество корней, которые необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="1c6f6-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="1c6f6-108">Корни</span><span class="sxs-lookup"><span data-stu-id="1c6f6-108">roots</span></span>  
 <span data-ttu-id="1c6f6-109">(ваут) Массив указателей, каждый из которых указывает на [COR_GC_REFERENCE](cor-gc-reference-structure.md) объект, представляющий корень объекта, который будет собран мусором.</span><span class="sxs-lookup"><span data-stu-id="1c6f6-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="1c6f6-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="1c6f6-110">pceltFetched</span></span>  
 <span data-ttu-id="1c6f6-111">(ваут) Указатель на количество [COR_GC_REFERENCE](cor-gc-reference-structure.md) объектов `roots`фактически вернулся в .</span><span class="sxs-lookup"><span data-stu-id="1c6f6-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="1c6f6-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="1c6f6-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c6f6-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c6f6-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c6f6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1c6f6-114">Requirements</span></span>  
 <span data-ttu-id="1c6f6-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c6f6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c6f6-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c6f6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c6f6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c6f6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c6f6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c6f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6f6-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c6f6-119">See also</span></span>

- [<span data-ttu-id="1c6f6-120">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="1c6f6-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="1c6f6-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1c6f6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
