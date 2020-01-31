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
ms.openlocfilehash: 3d27cf1987d7e9896885f87857554f4039c8d714
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788980"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="c6499-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="c6499-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="c6499-103">Инициализирует объект `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="c6499-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6499-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6499-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c6499-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="c6499-105">Remarks</span></span>  
 <span data-ttu-id="c6499-106">Отладчик должен вызвать `Initialize` во время создания, чтобы инициализировать службы отладки.</span><span class="sxs-lookup"><span data-stu-id="c6499-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="c6499-107">Этот метод должен вызываться до вызова любого другого метода `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="c6499-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6499-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c6499-108">Requirements</span></span>  
 <span data-ttu-id="c6499-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6499-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6499-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6499-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6499-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6499-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6499-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6499-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6499-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6499-113">See also</span></span>

- [<span data-ttu-id="c6499-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c6499-114">ICorDebug Interface</span></span>](icordebug-interface.md)
