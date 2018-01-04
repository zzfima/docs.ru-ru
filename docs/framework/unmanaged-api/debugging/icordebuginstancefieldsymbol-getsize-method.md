---
title: "Метод ICorDebugInstanceFieldSymbol::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad13dbe8148d4d9507c6a450d2833da049e0e13a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="b944e-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="b944e-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="b944e-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="b944e-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b944e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b944e-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b944e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b944e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="b944e-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="b944e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b944e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b944e-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b944e-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b944e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b944e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b944e-109">Requirements</span></span>  
 <span data-ttu-id="b944e-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b944e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b944e-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b944e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b944e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b944e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b944e-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b944e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b944e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b944e-114">See Also</span></span>  
 [<span data-ttu-id="b944e-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b944e-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="b944e-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b944e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
