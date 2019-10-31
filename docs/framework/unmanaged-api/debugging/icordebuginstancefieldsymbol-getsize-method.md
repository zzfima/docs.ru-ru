---
title: 'Метод ICorDebugInstanceFieldSymbol:: resize'
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 71828cd8486e2ff09190d23473dbab303b92f933
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139022"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="24d14-102">Метод ICorDebugInstanceFieldSymbol:: resize</span><span class="sxs-lookup"><span data-stu-id="24d14-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="24d14-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="24d14-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24d14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24d14-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24d14-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="24d14-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="24d14-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24d14-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="24d14-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24d14-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="24d14-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24d14-109">Требования</span><span class="sxs-lookup"><span data-stu-id="24d14-109">Requirements</span></span>  
 <span data-ttu-id="24d14-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24d14-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24d14-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24d14-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24d14-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24d14-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24d14-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24d14-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d14-114">См. также</span><span class="sxs-lookup"><span data-stu-id="24d14-114">See also</span></span>

- [<span data-ttu-id="24d14-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="24d14-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="24d14-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="24d14-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
