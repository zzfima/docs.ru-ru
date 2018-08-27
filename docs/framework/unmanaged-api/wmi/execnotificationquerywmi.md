---
title: Функция ExecNotificationQueryWmi (Справочник по неуправляемым API)
description: Функция ExecNotificationQueryWmi выполняет запрос для получения событий.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d314d85e7c1297636e8dd5cecaf050a527151518
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932803"
---
# <a name="execnotificationquerywmi-function"></a>Функция ExecNotificationQueryWmi
Выполняет запрос для получения событий. Вызов возвращается немедленно, а вызывающий объект может опросить возвращенном перечислителе для событий, при их поступлении. Освобождение возвращенном перечислителе отменяет запрос.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>Параметры

`strQueryLanguage`    
[in] Строка с допустимым запросом язык, поддерживаемый управления Windows. Оно должно быть «WQL», сокращение для языка запросов WMI.

`strQuery`  
[in] Текст запроса. Этот параметр не может быть `null`.

`lFlags`   
[in] Комбинация из следующих двух флагов, влияющих на поведение этой функции. Эти значения определены в *WbemCli.h* файл заголовка, или их можно определить как константы в коде. 

| Константа | Значение  | Описание:  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Этот флаг приводит к Полусинхронный вызов. Если этот флаг не установлен, вызов завершается ошибкой. Это обусловлено их получения постоянно, это означает, что пользователь должен опросить возвращенном перечислителе. Блокирует этот вызов бесконечно делает, невозможно. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Функция возвращает только вперед перечислителя. Обычно перечислители только вперед, выполняются быстрее и использовать меньше памяти, чем обычные перечислители, но они не допускают вызовы [клона](clone.md). |

`pCtx`  
[in] Как правило, это значение равно `null`. В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) экземпляр, который может использоваться поставщиком, предоставляющего запрошенные события. 

`ppEnum`  
[out] При отсутствии ошибок, получающей указатель на перечислитель, который позволяет вызывающей стороне для получения экземпляров в результирующем наборе запроса. См. в разделе ["Примечания"](#remarks) Дополнительные сведения.

`authLevel`  
[in] Уровень авторизации.

`impLevel` [in] Уровень олицетворения.

`pCurrentNamespace`   
[in] Указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объект, представляющий текущее пространство имен.

`strUser`   
[in] Имя пользователя. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

`strPassword`   
[in] Пароль. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

`strAuthority`   
[in] Имя домена пользователя. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть. |
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | Запрос указывает класс, который не существует. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | Запрошено слишком много точности в доставку событий. Должно быть указано больше погрешность опроса. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | Requess запросов, которые можно предоставить больше информации, чем управления Windows. Это `HRESULT` возвращается при запросе событий приводит к запросу, чтобы опросить все объекты в пространстве имен. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Запрос содержит синтаксическую ошибку. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Запрошенный язык запросов не поддерживается. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Запрос является слишком сложным. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI был, вероятно, остановлена или перезапустить. Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | Невозможно проанализировать запрос. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) метод.

После возврата функции, вызывающий объект периодически передает возвращенного `ppEnum` объект [Далее](next.md) функцию, чтобы увидеть, если все события будут доступны.

Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL. Большое количество WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки в виде `HRESULT` значение. Ограничение ключевых слов WQL зависит от того, насколько сложным является запрос.

Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
