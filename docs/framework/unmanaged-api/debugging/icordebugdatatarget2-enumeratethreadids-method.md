---
title: Метод ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 120a970aac33b1ab06ae47335a959d2791f893ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178980"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="02a3e-102">Метод ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="02a3e-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="02a3e-103">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="02a3e-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a3e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02a3e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a3e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02a3e-105">Parameters</span></span>  
 <span data-ttu-id="02a3e-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="02a3e-106">cThreadIDs</span></span>  
 <span data-ttu-id="02a3e-107">[входной] Максимальное число потоков, идентификаторы которых могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="02a3e-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="02a3e-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="02a3e-108">pcThreadIds</span></span>  
 <span data-ttu-id="02a3e-109">[выходной] Указатель на `ULONG32`, который указывает фактическое количество идентификаторов потоков, записанных в массив `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="02a3e-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="02a3e-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="02a3e-110">pThreadIDs</span></span>  
 <span data-ttu-id="02a3e-111">Массив идентификаторов потоков.</span><span class="sxs-lookup"><span data-stu-id="02a3e-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a3e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="02a3e-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02a3e-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="02a3e-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a3e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="02a3e-114">Requirements</span></span>  
 <span data-ttu-id="02a3e-115">**Платформы:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md). **Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02a3e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02a3e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02a3e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02a3e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a3e-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a3e-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="02a3e-118">See also</span></span>

- [<span data-ttu-id="02a3e-119">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="02a3e-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="02a3e-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="02a3e-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
