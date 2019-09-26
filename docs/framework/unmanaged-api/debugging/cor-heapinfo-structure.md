---
title: Структура COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7b340a73aa9eaebca9c0d78563ae298557039b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274194"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="c2534-102">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="c2534-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="c2534-103">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="c2534-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2534-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2534-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c2534-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c2534-105">Members</span></span>  
  
|<span data-ttu-id="c2534-106">Член</span><span class="sxs-lookup"><span data-stu-id="c2534-106">Member</span></span>|<span data-ttu-id="c2534-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c2534-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="c2534-108">`true`значение, если структуры сборки мусора являются допустимыми и можно перечислить в куче. в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="c2534-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="c2534-109">Размер указателей в байтах в целевой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="c2534-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="c2534-110">Количество куч логической сборки мусора в процессе.</span><span class="sxs-lookup"><span data-stu-id="c2534-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="c2534-111">`TRUE`Если включена одновременная (фоновая) сборка мусора; в противном случае —. `FALSE`</span><span class="sxs-lookup"><span data-stu-id="c2534-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="c2534-112">Член перечисления [CorDebugGCType](cordebuggctype-enumeration.md) , указывающий, работает ли сборщик мусора на рабочей станции или сервере.</span><span class="sxs-lookup"><span data-stu-id="c2534-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2534-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2534-113">Remarks</span></span>  
 <span data-ttu-id="c2534-114">Экземпляр `COR_HEAPINFO` структуры возвращается путем вызова метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c2534-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="c2534-115">Перед перечислением объектов в куче сборки мусора необходимо всегда проверять `areGCStructuresValid` поле, чтобы убедиться в том, что куча находится в перечислимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="c2534-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="c2534-116">Дополнительные сведения см. в описании метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c2534-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2534-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c2534-117">Requirements</span></span>  
 <span data-ttu-id="c2534-118">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2534-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2534-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c2534-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2534-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="c2534-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2534-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2534-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2534-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c2534-122">See also</span></span>

- [<span data-ttu-id="c2534-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="c2534-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c2534-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="c2534-124">Debugging</span></span>](index.md)
