---
title: Интерфейс ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 6506b11d97490f796486729dbeb612e47762b60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111439"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="f6735-102">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="f6735-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="f6735-103">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="f6735-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6735-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f6735-104">Methods</span></span>  
  
|<span data-ttu-id="f6735-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f6735-105">Method</span></span>|<span data-ttu-id="f6735-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f6735-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6735-107">Метод OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="f6735-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="f6735-108">Возвращает интерфейс "ICorDebugProcess", соответствующий модулю среды CLR, загруженному в процессе.</span><span class="sxs-lookup"><span data-stu-id="f6735-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="f6735-109">Метод CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="f6735-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="f6735-110">Определяет, используется ли по-прежнему Библиотека, предоставленная интерфейсом [иклрдебуггинглибрарипровидер](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) , или она может быть выгружена.</span><span class="sxs-lookup"><span data-stu-id="f6735-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6735-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="f6735-111">Remarks</span></span>  
 <span data-ttu-id="f6735-112">Экземпляр интерфейса `ICLRDebugging` можно получить с помощью функции [клркреатеинстанце](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f6735-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6735-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f6735-113">Requirements</span></span>  
 <span data-ttu-id="f6735-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6735-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6735-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6735-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6735-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6735-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6735-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6735-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6735-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f6735-118">See also</span></span>

- [<span data-ttu-id="f6735-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f6735-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f6735-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="f6735-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
