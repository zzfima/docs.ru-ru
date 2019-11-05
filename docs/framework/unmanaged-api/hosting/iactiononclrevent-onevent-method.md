---
title: Метод IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126920"
---
# <a name="iactiononclreventonevent-method"></a>Метод IActionOnCLREvent::OnEvent
Выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `event`  
 окне Одно из значений [еклревент](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) , указывающее тип события.  
  
 `data`  
 окне Указатель на объект, содержащий сведения о `event`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OnEvent` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы любого метода размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 Параметр `data` является указателем на объект неопределенного типа. Если параметр `event` имеет значение `Event_DomainUnload`, `data` является числовым идентификатором для выгрузки <xref:System.AppDomain>. Узел может предпринять соответствующие действия, используя этот идентификатор в качестве ключа.  
  
 Если `event` имеет `Event_MDAFired`, `data` является указателем на экземпляр [мдаинфо](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) , который содержит выходные данные сообщения от помощника по отладке управляемого кода (MDA). MDA — это функция среды CLR, которая помогает разработчикам выполнять отладку путем создания сообщений XML о событиях, которые в противном случае сложны для перехвата. Такие сообщения могут быть особенно полезны при отладке переходов между управляемым и неуправляемым кодом. Дополнительные сведения см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Перечисление EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [Интерфейс IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [Структура MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
