---
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136985"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="8cbdf-102">Метод ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="8cbdf-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="8cbdf-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="8cbdf-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cbdf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cbdf-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cbdf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cbdf-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8cbdf-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="8cbdf-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cbdf-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8cbdf-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8cbdf-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8cbdf-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cbdf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8cbdf-109">Requirements</span></span>  
 <span data-ttu-id="8cbdf-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cbdf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cbdf-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cbdf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cbdf-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cbdf-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8cbdf-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8cbdf-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8cbdf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8cbdf-114">See also</span></span>

- [<span data-ttu-id="8cbdf-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="8cbdf-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="8cbdf-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8cbdf-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
