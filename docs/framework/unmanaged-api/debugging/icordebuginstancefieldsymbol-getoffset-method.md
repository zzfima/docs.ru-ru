---
title: Метод ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 453f691f414050905f5d73e201ebeed79e2aaf50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910207"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="106a8-102">Метод ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="106a8-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="106a8-103">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="106a8-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="106a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="106a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="106a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="106a8-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="106a8-106">Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.</span><span class="sxs-lookup"><span data-stu-id="106a8-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="106a8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="106a8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="106a8-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="106a8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="106a8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="106a8-109">Requirements</span></span>  
 <span data-ttu-id="106a8-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="106a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="106a8-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="106a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="106a8-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="106a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="106a8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="106a8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106a8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="106a8-114">See also</span></span>

- [<span data-ttu-id="106a8-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="106a8-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="106a8-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="106a8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
