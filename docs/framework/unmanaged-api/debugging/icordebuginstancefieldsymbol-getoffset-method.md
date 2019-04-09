---
title: Метод ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8ea777755aebb59f3e865df26c38c74ef68ae31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203877"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="6f3bf-102">Метод ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="6f3bf-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="6f3bf-103">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="6f3bf-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f3bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f3bf-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f3bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f3bf-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="6f3bf-106">Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.</span><span class="sxs-lookup"><span data-stu-id="6f3bf-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f3bf-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f3bf-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f3bf-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6f3bf-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f3bf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6f3bf-109">Requirements</span></span>  
 <span data-ttu-id="6f3bf-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f3bf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f3bf-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f3bf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f3bf-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f3bf-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6f3bf-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6f3bf-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f3bf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6f3bf-114">See also</span></span>

- [<span data-ttu-id="6f3bf-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="6f3bf-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="6f3bf-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6f3bf-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
