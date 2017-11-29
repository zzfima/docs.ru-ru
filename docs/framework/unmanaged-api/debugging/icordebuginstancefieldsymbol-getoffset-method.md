---
title: "Метод ICorDebugInstanceFieldSymbol::GetOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 534e3238a4b20e390c4f2168629e0ba93620f55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="d7971-102">Метод ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="d7971-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="d7971-103">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="d7971-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7971-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7971-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7971-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7971-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="d7971-106">Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.</span><span class="sxs-lookup"><span data-stu-id="d7971-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7971-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7971-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7971-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d7971-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7971-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d7971-109">Requirements</span></span>  
 <span data-ttu-id="d7971-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7971-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7971-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7971-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7971-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7971-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7971-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7971-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7971-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d7971-114">See Also</span></span>  
 [<span data-ttu-id="d7971-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="d7971-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="d7971-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d7971-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
