---
title: Метод ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081454"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="2c147-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="2c147-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="2c147-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="2c147-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c147-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c147-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c147-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c147-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="2c147-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="2c147-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c147-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c147-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c147-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="2c147-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c147-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2c147-109">Requirements</span></span>  
 <span data-ttu-id="2c147-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c147-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c147-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c147-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c147-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c147-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c147-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c147-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c147-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2c147-114">See also</span></span>

- [<span data-ttu-id="2c147-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="2c147-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2c147-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2c147-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
