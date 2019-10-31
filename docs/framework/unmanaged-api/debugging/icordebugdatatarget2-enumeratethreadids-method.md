---
title: Метод ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: b4510e6858045281a2a663095972b84c40df3a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122160"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="389ae-102">Метод ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="389ae-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="389ae-103">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="389ae-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="389ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="389ae-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="389ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="389ae-105">Parameters</span></span>  
 <span data-ttu-id="389ae-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="389ae-106">cThreadIDs</span></span>  
 <span data-ttu-id="389ae-107">[входной] Максимальное число потоков, идентификаторы которых могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="389ae-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="389ae-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="389ae-108">pcThreadIds</span></span>  
 <span data-ttu-id="389ae-109">[выходной] Указатель на `ULONG32`, который указывает фактическое количество идентификаторов потоков, записанных в массив `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="389ae-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="389ae-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="389ae-110">pThreadIDs</span></span>  
 <span data-ttu-id="389ae-111">Массив идентификаторов потоков.</span><span class="sxs-lookup"><span data-stu-id="389ae-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="389ae-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="389ae-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="389ae-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="389ae-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="389ae-114">Требования</span><span class="sxs-lookup"><span data-stu-id="389ae-114">Requirements</span></span>  
 <span data-ttu-id="389ae-115">**Платформы:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md). **Заголовок:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="389ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="389ae-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="389ae-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="389ae-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="389ae-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="389ae-118">См. также</span><span class="sxs-lookup"><span data-stu-id="389ae-118">See also</span></span>

- [<span data-ttu-id="389ae-119">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="389ae-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="389ae-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="389ae-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
