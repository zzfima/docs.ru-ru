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
ms.openlocfilehash: e54611a38193a05a33381e798a61977d7aec41a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="d32fc-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="d32fc-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="d32fc-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="d32fc-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d32fc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d32fc-104">Methods</span></span>  
  
|<span data-ttu-id="d32fc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d32fc-105">Method</span></span>|<span data-ttu-id="d32fc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d32fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d32fc-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="d32fc-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="d32fc-108">Предоставляет перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры, обеспечивающие поток сведений о блокировании.</span><span class="sxs-lookup"><span data-stu-id="d32fc-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="d32fc-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="d32fc-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="d32fc-110">Указывает, является ли поток возникало необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="d32fc-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="d32fc-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="d32fc-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="d32fc-112">Возвращает текущий [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) объекта в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="d32fc-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d32fc-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="d32fc-113">Remarks</span></span>  
 <span data-ttu-id="d32fc-114">Этот интерфейс является логическим расширением интерфейса ICorDebugThread ICorDebugThread2, и [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d32fc-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d32fc-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d32fc-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d32fc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d32fc-116">Requirements</span></span>  
 <span data-ttu-id="d32fc-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d32fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d32fc-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d32fc-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d32fc-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d32fc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d32fc-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d32fc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32fc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d32fc-121">See Also</span></span>  
 [<span data-ttu-id="d32fc-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d32fc-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d32fc-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="d32fc-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
