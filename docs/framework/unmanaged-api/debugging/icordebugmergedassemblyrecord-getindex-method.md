---
title: 'Метод Икордебугмержедассемблирекорд:: with index'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 236bd8b22d6c3ec783d787f6c906ede3193cfc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131411"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="063f3-102">Метод Икордебугмержедассемблирекорд:: with index</span><span class="sxs-lookup"><span data-stu-id="063f3-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="063f3-103">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="063f3-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="063f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="063f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="063f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="063f3-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="063f3-106">[out] Указатель на индекс префикса.</span><span class="sxs-lookup"><span data-stu-id="063f3-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="063f3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="063f3-107">Remarks</span></span>  
 <span data-ttu-id="063f3-108">Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="063f3-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="063f3-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="063f3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="063f3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="063f3-110">Requirements</span></span>  
 <span data-ttu-id="063f3-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="063f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="063f3-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="063f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="063f3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="063f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="063f3-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="063f3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063f3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="063f3-115">See also</span></span>

- [<span data-ttu-id="063f3-116">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="063f3-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="063f3-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="063f3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
