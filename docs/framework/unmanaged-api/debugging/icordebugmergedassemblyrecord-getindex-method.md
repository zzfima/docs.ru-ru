---
title: "Метод ICorDebugMergedAssemblyRecord::GetIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dac64c785077fc3901e712498e66e11b9c9f3279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="95867-102">Метод ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="95867-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="95867-103">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="95867-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95867-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95867-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95867-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95867-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="95867-106">[out] Указатель на индекс префикса.</span><span class="sxs-lookup"><span data-stu-id="95867-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95867-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="95867-107">Remarks</span></span>  
 <span data-ttu-id="95867-108">Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="95867-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95867-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="95867-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95867-110">Требования</span><span class="sxs-lookup"><span data-stu-id="95867-110">Requirements</span></span>  
 <span data-ttu-id="95867-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95867-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95867-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95867-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95867-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95867-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95867-114">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95867-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95867-115">См. также</span><span class="sxs-lookup"><span data-stu-id="95867-115">See Also</span></span>  
 [<span data-ttu-id="95867-116">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="95867-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="95867-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="95867-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
