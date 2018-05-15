---
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa816ea9e6185791e09bcdb0e47c50761a5ebc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="37c79-102">Метод ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="37c79-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="37c79-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="37c79-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37c79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37c79-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37c79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37c79-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="37c79-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="37c79-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37c79-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="37c79-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="37c79-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="37c79-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37c79-109">Требования</span><span class="sxs-lookup"><span data-stu-id="37c79-109">Requirements</span></span>  
 <span data-ttu-id="37c79-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37c79-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37c79-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37c79-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37c79-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37c79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37c79-113">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37c79-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c79-114">См. также</span><span class="sxs-lookup"><span data-stu-id="37c79-114">See Also</span></span>  
 [<span data-ttu-id="37c79-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="37c79-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="37c79-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="37c79-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
