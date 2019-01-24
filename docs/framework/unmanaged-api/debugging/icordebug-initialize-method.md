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
ms.openlocfilehash: f7b4cf6c50d624f82a75f19b8e3f42c73910c4e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709303"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="229b1-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="229b1-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="229b1-103">Инициализирует `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="229b1-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="229b1-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="229b1-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="229b1-105">Remarks</span></span>  
 <span data-ttu-id="229b1-106">Отладчик должен вызвать `Initialize` во время создания службы времени для инициализации отладки.</span><span class="sxs-lookup"><span data-stu-id="229b1-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="229b1-107">Этот метод должен вызываться перед вызовом любого другого метода на `ICorDebug` вызывается.</span><span class="sxs-lookup"><span data-stu-id="229b1-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="229b1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="229b1-108">Requirements</span></span>  
 <span data-ttu-id="229b1-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="229b1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="229b1-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="229b1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="229b1-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="229b1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="229b1-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="229b1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229b1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="229b1-113">See also</span></span>
- [<span data-ttu-id="229b1-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="229b1-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
