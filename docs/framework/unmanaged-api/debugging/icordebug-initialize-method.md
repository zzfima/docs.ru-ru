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
ms.openlocfilehash: a5cda98cac0bc3fc6fb101fd0404b062224cb578
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134081"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="a6872-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="a6872-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="a6872-103">Инициализирует объект `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="a6872-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6872-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6872-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6872-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="a6872-105">Remarks</span></span>  
 <span data-ttu-id="a6872-106">Отладчик должен вызвать `Initialize` во время создания, чтобы инициализировать службы отладки.</span><span class="sxs-lookup"><span data-stu-id="a6872-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="a6872-107">Этот метод должен вызываться до вызова любого другого метода `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="a6872-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6872-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a6872-108">Requirements</span></span>  
 <span data-ttu-id="a6872-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6872-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6872-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6872-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6872-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6872-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6872-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6872-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6872-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a6872-113">See also</span></span>

- [<span data-ttu-id="a6872-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a6872-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
