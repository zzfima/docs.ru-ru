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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791337"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="52a00-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="52a00-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="52a00-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="52a00-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52a00-104">Методы</span><span class="sxs-lookup"><span data-stu-id="52a00-104">Methods</span></span>  
  
|<span data-ttu-id="52a00-105">Метод</span><span class="sxs-lookup"><span data-stu-id="52a00-105">Method</span></span>|<span data-ttu-id="52a00-106">Описание</span><span class="sxs-lookup"><span data-stu-id="52a00-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52a00-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="52a00-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="52a00-108">Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="52a00-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="52a00-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="52a00-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="52a00-110">Указывает, имел ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="52a00-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="52a00-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="52a00-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="52a00-112">Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="52a00-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52a00-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="52a00-113">Remarks</span></span>  
 <span data-ttu-id="52a00-114">Этот интерфейс является логическим расширением интерфейсов ICorDebugThread, ICorDebugThread2 и [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="52a00-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52a00-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="52a00-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a00-116">Требования</span><span class="sxs-lookup"><span data-stu-id="52a00-116">Requirements</span></span>  
 <span data-ttu-id="52a00-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a00-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a00-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52a00-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52a00-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52a00-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52a00-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a00-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a00-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="52a00-121">See also</span></span>

- [<span data-ttu-id="52a00-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="52a00-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="52a00-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="52a00-123">Debugging</span></span>](index.md)
