---
title: Метод ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3073abb3b9a44cccba323f282859c97c96bdf91d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760106"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="4ff67-102">Метод ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="4ff67-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="4ff67-103">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="4ff67-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ff67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ff67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ff67-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ff67-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="4ff67-106">Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.</span><span class="sxs-lookup"><span data-stu-id="4ff67-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ff67-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ff67-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ff67-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4ff67-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff67-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4ff67-109">Requirements</span></span>  
 <span data-ttu-id="4ff67-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff67-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff67-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ff67-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ff67-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ff67-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ff67-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff67-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff67-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4ff67-114">See also</span></span>

- [<span data-ttu-id="4ff67-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="4ff67-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="4ff67-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4ff67-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
