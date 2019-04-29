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
ms.openlocfilehash: dd09ce27c0fea9dca8fd86afc563651d68542e13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786364"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="9f8ba-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="9f8ba-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="9f8ba-103">Инициализирует `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="9f8ba-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f8ba-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9f8ba-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f8ba-105">Remarks</span></span>  
 <span data-ttu-id="9f8ba-106">Отладчик должен вызвать `Initialize` во время создания службы времени для инициализации отладки.</span><span class="sxs-lookup"><span data-stu-id="9f8ba-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="9f8ba-107">Этот метод должен вызываться перед вызовом любого другого метода на `ICorDebug` вызывается.</span><span class="sxs-lookup"><span data-stu-id="9f8ba-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f8ba-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9f8ba-108">Requirements</span></span>  
 <span data-ttu-id="9f8ba-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f8ba-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f8ba-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f8ba-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f8ba-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f8ba-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f8ba-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f8ba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8ba-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9f8ba-113">See also</span></span>

- [<span data-ttu-id="9f8ba-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9f8ba-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
