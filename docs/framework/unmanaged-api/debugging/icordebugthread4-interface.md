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
ms.openlocfilehash: 5d66a1aed1936d0146d42c8e4a5ad06dfa39c802
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962966"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="b2fb8-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="b2fb8-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="b2fb8-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2fb8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b2fb8-104">Methods</span></span>  
  
|<span data-ttu-id="b2fb8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b2fb8-105">Method</span></span>|<span data-ttu-id="b2fb8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b2fb8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2fb8-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="b2fb8-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="b2fb8-108">Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="b2fb8-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="b2fb8-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="b2fb8-110">Указывает, имел ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="b2fb8-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="b2fb8-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="b2fb8-112">Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2fb8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2fb8-113">Remarks</span></span>  
 <span data-ttu-id="b2fb8-114">Этот интерфейс является логическим расширением интерфейсов ICorDebugThread, ICorDebugThread2 и [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b2fb8-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2fb8-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2fb8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b2fb8-116">Requirements</span></span>  
 <span data-ttu-id="b2fb8-117">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2fb8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2fb8-118">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b2fb8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2fb8-119">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="b2fb8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2fb8-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2fb8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fb8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b2fb8-121">See also</span></span>

- [<span data-ttu-id="b2fb8-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b2fb8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b2fb8-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="b2fb8-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
