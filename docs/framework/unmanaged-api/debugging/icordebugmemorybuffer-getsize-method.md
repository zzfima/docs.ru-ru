---
title: Метод ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d687f2bbd3c20564368d4246961b56382ea14cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099681"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="8e93b-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="8e93b-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="8e93b-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="8e93b-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e93b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e93b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e93b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e93b-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="8e93b-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="8e93b-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e93b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e93b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e93b-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8e93b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e93b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8e93b-109">Requirements</span></span>  
 <span data-ttu-id="8e93b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e93b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e93b-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e93b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e93b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e93b-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8e93b-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8e93b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e93b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8e93b-114">See also</span></span>

- [<span data-ttu-id="8e93b-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="8e93b-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="8e93b-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8e93b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
