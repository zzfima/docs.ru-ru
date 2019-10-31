---
title: Интерфейс ICLRDebuggingLibraryProvider
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: 81b9ffe5979ad553a5bdfbc27111469b2ff4db6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111380"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="2f745-102">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="2f745-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="2f745-103">Включает метод [метода ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.</span><span class="sxs-lookup"><span data-stu-id="2f745-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f745-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2f745-104">Methods</span></span>  
  
|<span data-ttu-id="2f745-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2f745-105">Method</span></span>|<span data-ttu-id="2f745-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2f745-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f745-107">Метод ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="2f745-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="2f745-108">Позволяет отладчику предоставлять обработчик для модуля, который можно использовать для загрузки библиотеки отладки.</span><span class="sxs-lookup"><span data-stu-id="2f745-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f745-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2f745-109">Requirements</span></span>  
 <span data-ttu-id="2f745-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f745-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f745-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f745-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f745-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f745-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f745-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f745-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f745-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2f745-114">See also</span></span>

- [<span data-ttu-id="2f745-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2f745-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2f745-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="2f745-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
