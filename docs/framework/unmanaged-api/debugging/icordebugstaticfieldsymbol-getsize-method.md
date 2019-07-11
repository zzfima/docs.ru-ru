---
title: Метод ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a30778a287b4115df552444549a92c006288005
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760750"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="64ddd-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="64ddd-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="64ddd-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="64ddd-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ddd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64ddd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64ddd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64ddd-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="64ddd-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="64ddd-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64ddd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="64ddd-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64ddd-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="64ddd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ddd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="64ddd-109">Requirements</span></span>  
 <span data-ttu-id="64ddd-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64ddd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ddd-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64ddd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64ddd-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64ddd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64ddd-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ddd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ddd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="64ddd-114">See also</span></span>

- [<span data-ttu-id="64ddd-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="64ddd-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="64ddd-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="64ddd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
