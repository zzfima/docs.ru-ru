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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c62079a87c09bcbe09167a137fd39530652ae3e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697866"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="9d91d-102">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="9d91d-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="9d91d-103">Включает в себя [метод ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет библиотеки отладки конкретной версии среды выполнения, находить и загружать по мере необходимости поставщика библиотеки.</span><span class="sxs-lookup"><span data-stu-id="9d91d-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d91d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9d91d-104">Methods</span></span>  
  
|<span data-ttu-id="9d91d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9d91d-105">Method</span></span>|<span data-ttu-id="9d91d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9d91d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d91d-107">Метод ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="9d91d-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="9d91d-108">Позволяет отладчику предоставить дескриптор модуля, который может использоваться для загрузки библиотеки отладки.</span><span class="sxs-lookup"><span data-stu-id="9d91d-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d91d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9d91d-109">Requirements</span></span>  
 <span data-ttu-id="9d91d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d91d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d91d-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d91d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d91d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d91d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d91d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d91d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d91d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9d91d-114">See also</span></span>

- [<span data-ttu-id="9d91d-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9d91d-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9d91d-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="9d91d-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
