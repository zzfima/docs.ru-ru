---
title: Метод ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 51c13b67951c714d1aec602ffea22891328565a0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793178"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="ec3da-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="ec3da-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="ec3da-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="ec3da-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec3da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec3da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec3da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec3da-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="ec3da-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="ec3da-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec3da-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="ec3da-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec3da-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="ec3da-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec3da-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ec3da-109">Requirements</span></span>  
 <span data-ttu-id="ec3da-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec3da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec3da-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec3da-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec3da-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec3da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec3da-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec3da-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3da-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec3da-114">See also</span></span>

- [<span data-ttu-id="ec3da-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="ec3da-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="ec3da-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ec3da-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
