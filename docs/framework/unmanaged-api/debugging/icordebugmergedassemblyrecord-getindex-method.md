---
title: Метод ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0bcb5cdb4e93ae8ce6981bd86f125ecccb7d732
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414840"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="bcfe7-102">Метод ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="bcfe7-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="bcfe7-103">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="bcfe7-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfe7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcfe7-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcfe7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcfe7-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="bcfe7-106">[out] Указатель на индекс префикса.</span><span class="sxs-lookup"><span data-stu-id="bcfe7-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcfe7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcfe7-107">Remarks</span></span>  
 <span data-ttu-id="bcfe7-108">Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="bcfe7-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcfe7-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="bcfe7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfe7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bcfe7-110">Requirements</span></span>  
 <span data-ttu-id="bcfe7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcfe7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfe7-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcfe7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcfe7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcfe7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcfe7-114">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfe7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfe7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bcfe7-115">See Also</span></span>  
 [<span data-ttu-id="bcfe7-116">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="bcfe7-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="bcfe7-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bcfe7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
