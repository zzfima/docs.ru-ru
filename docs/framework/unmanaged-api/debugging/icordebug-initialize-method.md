---
title: Метод ICorDebug::Initialize
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80465c8d1f1f9e09c0675de1667b999b332b9f6b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738146"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="8238a-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="8238a-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="8238a-103">Инициализирует `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="8238a-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8238a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8238a-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8238a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8238a-105">Remarks</span></span>  
 <span data-ttu-id="8238a-106">Отладчик должен вызвать `Initialize` во время создания службы времени для инициализации отладки.</span><span class="sxs-lookup"><span data-stu-id="8238a-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="8238a-107">Этот метод должен вызываться перед вызовом любого другого метода на `ICorDebug` вызывается.</span><span class="sxs-lookup"><span data-stu-id="8238a-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8238a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8238a-108">Requirements</span></span>  
 <span data-ttu-id="8238a-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8238a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8238a-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8238a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8238a-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8238a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8238a-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8238a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8238a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8238a-113">See also</span></span>

- [<span data-ttu-id="8238a-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="8238a-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
