---
title: Метод ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c88d389f80b4b3d811d95f65acd41f294d076b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969080"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="5f4ec-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="5f4ec-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="5f4ec-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="5f4ec-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f4ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f4ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f4ec-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="5f4ec-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="5f4ec-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f4ec-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f4ec-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f4ec-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5f4ec-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f4ec-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5f4ec-109">Requirements</span></span>  
 <span data-ttu-id="5f4ec-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f4ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4ec-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5f4ec-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f4ec-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="5f4ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f4ec-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4ec-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4ec-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5f4ec-114">See also</span></span>

- [<span data-ttu-id="5f4ec-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="5f4ec-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="5f4ec-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5f4ec-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
