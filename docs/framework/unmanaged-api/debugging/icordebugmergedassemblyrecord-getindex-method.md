---
title: Метод ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c869c829acbfb9b0281537c7355229acbf2c5a7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752721"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="bdc78-102">Метод ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="bdc78-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="bdc78-103">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="bdc78-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdc78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdc78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdc78-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="bdc78-106">[out] Указатель на индекс префикса.</span><span class="sxs-lookup"><span data-stu-id="bdc78-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdc78-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdc78-107">Remarks</span></span>  
 <span data-ttu-id="bdc78-108">Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="bdc78-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdc78-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="bdc78-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc78-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bdc78-110">Requirements</span></span>  
 <span data-ttu-id="bdc78-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdc78-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc78-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdc78-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdc78-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdc78-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdc78-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc78-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc78-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bdc78-115">See also</span></span>

- [<span data-ttu-id="bdc78-116">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="bdc78-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bdc78-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bdc78-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
