---
title: "Метод ICorDebugMemoryBuffer::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a21198c70512af703e106870d1bc3f7882d62fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="e6af0-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="e6af0-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="e6af0-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="e6af0-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6af0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6af0-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6af0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6af0-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="e6af0-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="e6af0-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6af0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6af0-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6af0-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e6af0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6af0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e6af0-109">Requirements</span></span>  
 <span data-ttu-id="e6af0-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6af0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6af0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6af0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6af0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6af0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6af0-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6af0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6af0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e6af0-114">See Also</span></span>  
 [<span data-ttu-id="e6af0-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="e6af0-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="e6af0-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e6af0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
