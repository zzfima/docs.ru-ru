---
title: "Интерфейс ICorDebugThread4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4
helpviewer_keywords: ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0066fbda63e46442cc6b6b6547ad7f0393815840
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="a72a3-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="a72a3-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="a72a3-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="a72a3-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a72a3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a72a3-104">Methods</span></span>  
  
|<span data-ttu-id="a72a3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a72a3-105">Method</span></span>|<span data-ttu-id="a72a3-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="a72a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a72a3-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="a72a3-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="a72a3-108">Предоставляет перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры, обеспечивающие поток сведений о блокировании.</span><span class="sxs-lookup"><span data-stu-id="a72a3-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="a72a3-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="a72a3-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="a72a3-110">Указывает, является ли поток возникало необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="a72a3-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="a72a3-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="a72a3-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="a72a3-112">Возвращает текущий [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) объекта в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="a72a3-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a72a3-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a72a3-113">Remarks</span></span>  
 <span data-ttu-id="a72a3-114">Этот интерфейс является логическим расширением интерфейса ICorDebugThread ICorDebugThread2, и [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a72a3-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a72a3-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a72a3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a72a3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a72a3-116">Requirements</span></span>  
 <span data-ttu-id="a72a3-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a72a3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a72a3-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a72a3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a72a3-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a72a3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a72a3-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a72a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72a3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a72a3-121">See Also</span></span>  
 [<span data-ttu-id="a72a3-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a72a3-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a72a3-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="a72a3-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
