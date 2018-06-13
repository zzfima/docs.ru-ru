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
ms.openlocfilehash: fa79382d597d303d492e3a441c15a422697be279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405971"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="4f781-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="4f781-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="4f781-103">Инициализирует `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="4f781-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f781-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f781-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f781-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f781-105">Remarks</span></span>  
 <span data-ttu-id="4f781-106">Отладчик должен вызвать `Initialize` в момент создания службы времени для инициализации отладки.</span><span class="sxs-lookup"><span data-stu-id="4f781-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="4f781-107">Этот метод должен вызываться перед любой другой метод для `ICorDebug` вызывается.</span><span class="sxs-lookup"><span data-stu-id="4f781-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f781-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4f781-108">Requirements</span></span>  
 <span data-ttu-id="4f781-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f781-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f781-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f781-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f781-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f781-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f781-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f781-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f781-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4f781-113">See Also</span></span>  
 [<span data-ttu-id="4f781-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="4f781-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
