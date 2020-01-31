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
ms.openlocfilehash: a8d9348572ec0cf67c5facebb2053a7091661724
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793602"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="195c9-102">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="195c9-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="195c9-103">Включает метод [метода ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.</span><span class="sxs-lookup"><span data-stu-id="195c9-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="195c9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="195c9-104">Methods</span></span>  
  
|<span data-ttu-id="195c9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="195c9-105">Method</span></span>|<span data-ttu-id="195c9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="195c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="195c9-107">Метод ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="195c9-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="195c9-108">Позволяет отладчику предоставлять обработчик для модуля, который можно использовать для загрузки библиотеки отладки.</span><span class="sxs-lookup"><span data-stu-id="195c9-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="195c9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="195c9-109">Requirements</span></span>  
 <span data-ttu-id="195c9-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195c9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195c9-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="195c9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="195c9-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="195c9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195c9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195c9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195c9-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="195c9-114">See also</span></span>

- [<span data-ttu-id="195c9-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="195c9-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="195c9-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="195c9-116">Debugging</span></span>](index.md)
