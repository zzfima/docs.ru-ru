---
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: b6665df550a2d07a3fa84c3f2b6bf07f459cd713
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792205"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="6f285-102">Метод ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="6f285-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="6f285-103">Уведомляет [ICorDebug](icordebug-interface.md) о том, что процесс выполняется.</span><span class="sxs-lookup"><span data-stu-id="6f285-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f285-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f285-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f285-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f285-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="6f285-106">окне Член перечисления [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="6f285-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f285-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6f285-107">Remarks</span></span>  
 <span data-ttu-id="6f285-108">Отладчик вызывает этот метод, чтобы уведомить [ICorDebug](icordebug-interface.md) о том, что процесс выполняется.</span><span class="sxs-lookup"><span data-stu-id="6f285-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f285-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6f285-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f285-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6f285-110">Requirements</span></span>  
 <span data-ttu-id="6f285-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f285-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f285-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f285-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f285-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f285-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f285-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f285-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f285-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f285-115">See also</span></span>

- [<span data-ttu-id="6f285-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="6f285-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="6f285-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6f285-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
