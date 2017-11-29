---
title: "Метод ICorDebugStaticFieldSymbol::GetAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20c0c934772625d27057957d00e53fb4b485c4fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="4d47f-102">Метод ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="4d47f-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="4d47f-103">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="4d47f-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d47f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d47f-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d47f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d47f-105">Parameters</span></span>  
 <span data-ttu-id="4d47f-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="4d47f-106">pRVA</span></span>  
 <span data-ttu-id="4d47f-107">[out] Указатель на относительный виртуальный адрес (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="4d47f-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d47f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d47f-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d47f-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4d47f-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d47f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4d47f-110">Requirements</span></span>  
 <span data-ttu-id="4d47f-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d47f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d47f-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d47f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d47f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d47f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d47f-114">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d47f-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d47f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4d47f-115">See Also</span></span>  
 [<span data-ttu-id="4d47f-116">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="4d47f-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="4d47f-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4d47f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
