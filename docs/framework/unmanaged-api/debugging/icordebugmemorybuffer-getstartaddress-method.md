---
title: 'Метод Икордебугмеморибуффер:: Жетстартаддресс'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1394624051baa9e7dd21e29788d5fab28332081b
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987554"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="e18a6-102">Метод Икордебугмеморибуффер:: Жетстартаддресс</span><span class="sxs-lookup"><span data-stu-id="e18a6-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="e18a6-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="e18a6-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e18a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e18a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e18a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e18a6-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="e18a6-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="e18a6-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e18a6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e18a6-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="e18a6-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e18a6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e18a6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e18a6-109">Requirements</span></span>  
 <span data-ttu-id="e18a6-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e18a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e18a6-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e18a6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e18a6-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="e18a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e18a6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e18a6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e18a6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e18a6-114">See also</span></span>

- [<span data-ttu-id="e18a6-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="e18a6-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="e18a6-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e18a6-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
