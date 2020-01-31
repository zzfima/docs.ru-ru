---
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f2b09c847a6bf577b78c8155f85f07b93877fbe9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793171"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="6e4e8-102">Метод ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="6e4e8-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="6e4e8-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="6e4e8-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e4e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e4e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e4e8-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6e4e8-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="6e4e8-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e4e8-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6e4e8-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="6e4e8-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6e4e8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4e8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6e4e8-109">Requirements</span></span>  
 <span data-ttu-id="6e4e8-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e4e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e4e8-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e4e8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e4e8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e4e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e4e8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e4e8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4e8-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e4e8-114">See also</span></span>

- [<span data-ttu-id="6e4e8-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="6e4e8-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="6e4e8-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6e4e8-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
