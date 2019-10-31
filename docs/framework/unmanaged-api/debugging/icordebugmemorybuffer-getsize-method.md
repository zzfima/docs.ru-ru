---
title: 'Метод Икордебугмеморибуффер:: resize'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1693860abe99884ee443be0666dfb6b485a219a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127997"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="1364a-102">Метод Икордебугмеморибуффер:: resize</span><span class="sxs-lookup"><span data-stu-id="1364a-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="1364a-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="1364a-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1364a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1364a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1364a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1364a-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="1364a-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="1364a-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1364a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="1364a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1364a-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="1364a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1364a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1364a-109">Requirements</span></span>  
 <span data-ttu-id="1364a-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1364a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1364a-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1364a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1364a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1364a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1364a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1364a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1364a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1364a-114">See also</span></span>

- [<span data-ttu-id="1364a-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="1364a-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="1364a-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1364a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
