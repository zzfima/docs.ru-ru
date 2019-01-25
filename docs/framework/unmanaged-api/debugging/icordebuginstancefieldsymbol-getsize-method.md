---
title: Метод ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04d866888c15585ff5058f870257b317ac888be7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696988"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="9e41f-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="9e41f-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="9e41f-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="9e41f-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e41f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e41f-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e41f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e41f-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9e41f-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="9e41f-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e41f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e41f-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e41f-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9e41f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e41f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9e41f-109">Requirements</span></span>  
 <span data-ttu-id="9e41f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e41f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e41f-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e41f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e41f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e41f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e41f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e41f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e41f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9e41f-114">See also</span></span>
- [<span data-ttu-id="9e41f-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="9e41f-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="9e41f-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9e41f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
