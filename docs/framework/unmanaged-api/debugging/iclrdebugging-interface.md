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
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793633"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="0f674-102">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="0f674-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="0f674-103">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="0f674-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f674-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0f674-104">Methods</span></span>  
  
|<span data-ttu-id="0f674-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0f674-105">Method</span></span>|<span data-ttu-id="0f674-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0f674-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f674-107">Метод OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="0f674-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="0f674-108">Возвращает интерфейс "ICorDebugProcess", соответствующий модулю среды CLR, загруженному в процессе.</span><span class="sxs-lookup"><span data-stu-id="0f674-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="0f674-109">Метод CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="0f674-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="0f674-110">Определяет, используется ли по-прежнему Библиотека, предоставленная интерфейсом [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) , или она может быть выгружена.</span><span class="sxs-lookup"><span data-stu-id="0f674-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f674-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="0f674-111">Remarks</span></span>  
 <span data-ttu-id="0f674-112">Экземпляр интерфейса `ICLRDebugging` можно получить с помощью функции [клркреатеинстанце](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0f674-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f674-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0f674-113">Requirements</span></span>  
 <span data-ttu-id="0f674-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f674-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f674-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f674-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f674-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f674-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f674-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f674-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f674-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f674-118">See also</span></span>

- [<span data-ttu-id="0f674-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0f674-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0f674-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="0f674-120">Debugging</span></span>](index.md)
