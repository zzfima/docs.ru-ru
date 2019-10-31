---
title: 'Метод Икордебугмеморибуффер:: Жетстартаддресс'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: e2876398ceaf863bbb3c7e576d59b89c52f1bdaf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127987"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="00874-102">Метод Икордебугмеморибуффер:: Жетстартаддресс</span><span class="sxs-lookup"><span data-stu-id="00874-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="00874-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="00874-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00874-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00874-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00874-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00874-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="00874-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="00874-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00874-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="00874-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="00874-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="00874-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00874-109">Требования</span><span class="sxs-lookup"><span data-stu-id="00874-109">Requirements</span></span>  
 <span data-ttu-id="00874-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00874-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00874-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00874-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00874-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00874-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00874-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00874-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00874-114">См. также</span><span class="sxs-lookup"><span data-stu-id="00874-114">See also</span></span>

- [<span data-ttu-id="00874-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="00874-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="00874-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="00874-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
