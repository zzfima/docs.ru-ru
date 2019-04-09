---
title: Интерфейс ICorDebugThread4
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f213a35a12bfb5cc92558a76e122a1494d567f93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170804"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="a0627-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="a0627-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="a0627-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="a0627-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0627-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a0627-104">Methods</span></span>  
  
|<span data-ttu-id="a0627-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a0627-105">Method</span></span>|<span data-ttu-id="a0627-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a0627-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0627-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="a0627-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="a0627-108">Предоставляет перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) сведения о блокировании потока структуры, обеспечивающие.</span><span class="sxs-lookup"><span data-stu-id="a0627-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="a0627-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="a0627-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="a0627-110">Указывает, возникало ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="a0627-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="a0627-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="a0627-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="a0627-112">Получает текущий [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) объекта в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="a0627-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0627-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0627-113">Remarks</span></span>  
 <span data-ttu-id="a0627-114">Этот интерфейс является логическим расширением интерфейса ICorDebugThread, ICorDebugThread2, и [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a0627-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0627-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a0627-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0627-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a0627-116">Requirements</span></span>  
 <span data-ttu-id="a0627-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0627-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0627-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0627-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0627-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0627-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a0627-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a0627-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a0627-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a0627-121">See also</span></span>

- [<span data-ttu-id="a0627-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a0627-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a0627-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="a0627-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
