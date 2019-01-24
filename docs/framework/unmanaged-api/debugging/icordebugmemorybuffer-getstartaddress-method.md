---
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29149ceb155cdfdf7b735d6939809e80f2ba4dc0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695547"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="d75b0-102">Метод ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="d75b0-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="d75b0-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="d75b0-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d75b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d75b0-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d75b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d75b0-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d75b0-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="d75b0-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d75b0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d75b0-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d75b0-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d75b0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d75b0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d75b0-109">Requirements</span></span>  
 <span data-ttu-id="d75b0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d75b0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d75b0-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d75b0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d75b0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d75b0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d75b0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d75b0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75b0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d75b0-114">See also</span></span>
- [<span data-ttu-id="d75b0-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="d75b0-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d75b0-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d75b0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
