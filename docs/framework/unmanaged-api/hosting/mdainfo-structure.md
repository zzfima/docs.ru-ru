---
title: Структура MDAInfo
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123263"
---
# <a name="mdainfo-structure"></a>Структура MDAInfo
Предоставляет сведения о событии `Event_MDAFired`, которое активирует создание помощника по отладке управляемого кода (MDA).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`lpMDACaption`|Заголовок текущего MDA. Заголовок описывает тип сбоя, вызвавшего событие `Event_MDAFired`.|  
|`lpMDAMessage`|Выходное сообщение, предоставленное текущим MDA.|  
  
## <a name="remarks"></a>Заметки  
 Управляемые помощники по отладке (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для выполнения таких задач, как определение недопустимых условий в подсистеме выполнения среды выполнения или дамп дополнительных сведений о состоянии ядре. MDA создают сообщения XML о событиях, которые в противном случае сложны для перехвата. Они особенно полезны для отладки переходов между управляемым и неуправляемым кодом.  
  
 При срабатывании события, запускающего создание MDA, среда выполнения выполняет следующие действия:  
  
- Если узел не зарегистрировал экземпляр [иактиононклревент](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) , вызвав [ICLROnEventManager:: регистерактиононевент](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) , чтобы получать уведомления о событии `Event_MDAFired`, среда выполнения переходит по умолчанию, а не размещенное поведение.  
  
- Если узел зарегистрировал обработчик для этого события, среда выполнения проверяет, присоединен ли отладчик к процессу. Если это так, среда выполнения разбивается на отладчик. Когда отладчик продолжит выполнение, он вызывает узел. Если отладчик не присоединен, среда выполнения вызывает `IActionOnCLREvent::OnEvent` и передает указатель на экземпляр `MDAInfo` в качестве параметра `data`.  
  
 Узел может активировать MDA и получать уведомления при активации MDA. Это дает узлу возможность переопределить поведение по умолчанию и прервать управляемый поток, вызвавший событие, чтобы предотвратить повреждение состояния процесса. Дополнительные сведения об использовании MDA см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
