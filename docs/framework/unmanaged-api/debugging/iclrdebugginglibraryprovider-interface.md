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
ms.openlocfilehash: 7537d3d6f741f36ab81d73751963a8539de0a36c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404473"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="0d4c0-102">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="0d4c0-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="0d4c0-103">Включает в себя [метод ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет среды выполнения от версии библиотеки отладки находить и загружать по требованию библиотеки поставщика.</span><span class="sxs-lookup"><span data-stu-id="0d4c0-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d4c0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0d4c0-104">Methods</span></span>  
  
|<span data-ttu-id="0d4c0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0d4c0-105">Method</span></span>|<span data-ttu-id="0d4c0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0d4c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d4c0-107">Метод ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="0d4c0-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="0d4c0-108">Позволяет отладчику предоставить дескриптор модуля, который может использоваться для загрузки библиотеки отладки.</span><span class="sxs-lookup"><span data-stu-id="0d4c0-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d4c0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0d4c0-109">Requirements</span></span>  
 <span data-ttu-id="0d4c0-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d4c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d4c0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d4c0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d4c0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d4c0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d4c0-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d4c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4c0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0d4c0-114">See Also</span></span>  
 [<span data-ttu-id="0d4c0-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0d4c0-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0d4c0-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="0d4c0-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
