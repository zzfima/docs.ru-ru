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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a395579892ff2410865a4fcdd19cf20449b82b88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>Метод ICorDebugHeapValue3::GetMonitorEventWaitList
Предоставляет упорядоченный список потоков, которые находятся в очереди на события, связанного с блокировкой монитора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppThreadEnum`  
 [out] ICorDebugThreadEnum перечислитель, который предоставляет упорядоченный список потоков.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Список не пуст.|  
|S_FALSE|Список пуст.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 Первый поток в списке является первый поток, освобождаемый при следующем вызове <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>. Следующий поток в списке освобождается на следующий вызов и т. д.  
  
 Если список не пуст, этот метод возвращает значение S_OK. Если список пуст, метод возвращает значение S_FALSE; в этом случае перечисление действительными, несмотря на то, что он пуст.  
  
 В любом случае интерфейс перечисления может использоваться только в течение текущего синхронизированного состояния. Тем не менее выданных от него интерфейсы потока действуют до выхода потока.  
  
 Если `ppThreadEnum` не является допустимым указателем, результат будет неопределенным.  
  
 Если происходит ошибка, она не может определить, что, если таковые имеются, потоки ожидают монитора, метод возвращает значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
