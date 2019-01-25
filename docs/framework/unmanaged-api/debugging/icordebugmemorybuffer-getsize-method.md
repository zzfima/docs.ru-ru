---
title: Метод ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5984addb41c33468068f7ad24a15533f75dc367
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714728"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="47ff7-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="47ff7-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="47ff7-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="47ff7-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ff7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47ff7-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47ff7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47ff7-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="47ff7-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="47ff7-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47ff7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="47ff7-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47ff7-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="47ff7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47ff7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="47ff7-109">Requirements</span></span>  
 <span data-ttu-id="47ff7-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47ff7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47ff7-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47ff7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47ff7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47ff7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47ff7-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47ff7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ff7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="47ff7-114">See also</span></span>
- [<span data-ttu-id="47ff7-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="47ff7-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="47ff7-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="47ff7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
