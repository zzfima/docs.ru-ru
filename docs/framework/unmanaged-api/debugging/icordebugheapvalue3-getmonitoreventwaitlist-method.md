---
title: Метод ICorDebugHeapValue3::GetMonitorEventWaitList
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: 0fbff178efd4d0dff3593907b3d40e946be2ff6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121297"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="812a3-102">Метод ICorDebugHeapValue3::GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="812a3-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="812a3-103">Предоставляет упорядоченный список потоков, поставленных в очередь на событие, связанное с блокировкой монитора.</span><span class="sxs-lookup"><span data-stu-id="812a3-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="812a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="812a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="812a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="812a3-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="812a3-106">заполняет Перечислитель Икордебугсреаденум, предоставляющий упорядоченный список потоков.</span><span class="sxs-lookup"><span data-stu-id="812a3-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="812a3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="812a3-107">Return Value</span></span>  
 <span data-ttu-id="812a3-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="812a3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="812a3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="812a3-109">HRESULT</span></span>|<span data-ttu-id="812a3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="812a3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="812a3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="812a3-111">S_OK</span></span>|<span data-ttu-id="812a3-112">Список не пуст.</span><span class="sxs-lookup"><span data-stu-id="812a3-112">The list is not empty.</span></span>|  
|<span data-ttu-id="812a3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="812a3-113">S_FALSE</span></span>|<span data-ttu-id="812a3-114">Список пуст.</span><span class="sxs-lookup"><span data-stu-id="812a3-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="812a3-115">Исключения</span><span class="sxs-lookup"><span data-stu-id="812a3-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="812a3-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="812a3-116">Remarks</span></span>  
 <span data-ttu-id="812a3-117">Первый поток в списке является первым потоком, который освобождается при следующем вызове метода <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="812a3-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="812a3-118">Следующий поток в списке освобождается в следующем вызове и т. д.</span><span class="sxs-lookup"><span data-stu-id="812a3-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="812a3-119">Если список не пуст, этот метод возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="812a3-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="812a3-120">Если список пуст, метод возвращает значение S_FALSE; в этом случае перечисление по-прежнему является допустимым, хотя оно пустое.</span><span class="sxs-lookup"><span data-stu-id="812a3-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="812a3-121">В любом случае интерфейс перечисления можно использовать только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="812a3-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="812a3-122">Тем не менее, высветка интерфейсов потока является допустимой, пока поток не завершит работу.</span><span class="sxs-lookup"><span data-stu-id="812a3-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="812a3-123">Если `ppThreadEnum` не является допустимым указателем, результат не определен.</span><span class="sxs-lookup"><span data-stu-id="812a3-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="812a3-124">Если возникает ошибка, которая не может определить, какие потоки ожидают монитор, метод возвращает значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="812a3-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="812a3-125">Требования</span><span class="sxs-lookup"><span data-stu-id="812a3-125">Requirements</span></span>  
 <span data-ttu-id="812a3-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="812a3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="812a3-127">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="812a3-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="812a3-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="812a3-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="812a3-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="812a3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="812a3-130">См. также</span><span class="sxs-lookup"><span data-stu-id="812a3-130">See also</span></span>

- [<span data-ttu-id="812a3-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="812a3-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="812a3-132">Отладка</span><span class="sxs-lookup"><span data-stu-id="812a3-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
