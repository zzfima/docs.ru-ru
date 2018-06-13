---
title: Метод ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d915c7d5521e630602f4dac6c905920fd2fab9d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411451"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="210ba-102">Метод ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="210ba-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="210ba-103">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="210ba-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="210ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="210ba-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="210ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="210ba-105">Parameters</span></span>  
 <span data-ttu-id="210ba-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="210ba-106">cThreadIDs</span></span>  
 <span data-ttu-id="210ba-107">[входной] Максимальное число потоков, идентификаторы которых могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="210ba-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="210ba-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="210ba-108">pcThreadIds</span></span>  
 <span data-ttu-id="210ba-109">[выходной] Указатель на `ULONG32`, который указывает фактическое количество идентификаторов потоков, записанных в массив `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="210ba-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="210ba-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="210ba-110">pThreadIDs</span></span>  
 <span data-ttu-id="210ba-111">Массив идентификаторов потоков.</span><span class="sxs-lookup"><span data-stu-id="210ba-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="210ba-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="210ba-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="210ba-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="210ba-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="210ba-114">Требования</span><span class="sxs-lookup"><span data-stu-id="210ba-114">Requirements</span></span>  
 <span data-ttu-id="210ba-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md). **Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="210ba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="210ba-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="210ba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="210ba-117">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="210ba-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210ba-118">См. также</span><span class="sxs-lookup"><span data-stu-id="210ba-118">See Also</span></span>  
 [<span data-ttu-id="210ba-119">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="210ba-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="210ba-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="210ba-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
