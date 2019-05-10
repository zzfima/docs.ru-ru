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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faa6af54714f7f0b7ac91c7836673c163195d5f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656459"
---
# <a name="mdainfo-structure"></a>Структура MDAInfo
Предоставляет сведения о `Event_MDAFired` событие, которое инициирует создание помощник по отладке управляемого (кода MDA).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`lpMDACaption`|Название текущего MDA. Заголовок описывает тип ошибки, вызвавшей `Event_MDAFired` событий.|  
|`lpMDAMessage`|Выходное сообщение, предоставляемые текущего MDA.|  
  
## <a name="remarks"></a>Примечания  
 Средств отладки, в сочетании с общеязыковой среды выполнения (CLR) для выполнения задач, таких как идентификация недопустимых состояний в ядре выполнения среды выполнения или создания дампа Дополнительные сведения о состоянии управляемых помощников по отладке (MDA) модуль. Помощники отладки управляемого кода создавать XML-сообщений о событиях, которые в противном случае трудно ловушки. Они особенно полезны для отладки переходов между управляемым и неуправляемым кодом.  
  
 При возникновении события, которое инициирует создание MDA, среда выполнения выполняет следующие действия:  
  
- Если узел не зарегистрирован [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) экземпляра путем вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) для получения уведомлений об `Event_MDAFired` события, среда выполнения продолжает его по умолчанию, поведение без размещения.  
  
- Если узел зарегистрировал обработчик для этого события, среда выполнения проверяет, присоединен ли отладчик к процессу. В противном случае среда выполнения переключается в режим отладчика. Когда отладчик продолжает, она вызывает главное приложение. Если отладчик не присоединен, среда выполнения вызывает `IActionOnCLREvent::OnEvent` и передает указатель на `MDAInfo` экземпляр как `data` параметр.  
  
 Узел можно активировать MDA и получать уведомления при активации MDA. Это предоставляет узлу возможность переопределить поведение по умолчанию и отменить управляемый поток, который вызвал событие, чтобы предотвратить повреждение состояния процесса. Дополнительные сведения об использовании MDA, см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.idl  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
