---
title: "Метод ICorDebugStaticFieldSymbol::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 256a15952cd52c5a096e1f0b8c7fc2086cde226c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="cd188-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="cd188-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="cd188-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="cd188-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd188-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd188-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd188-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd188-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="cd188-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="cd188-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd188-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd188-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd188-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="cd188-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd188-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cd188-109">Requirements</span></span>  
 <span data-ttu-id="cd188-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd188-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd188-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd188-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd188-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd188-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd188-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd188-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd188-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cd188-114">See Also</span></span>  
 [<span data-ttu-id="cd188-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="cd188-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="cd188-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cd188-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
