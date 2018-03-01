---
title: "Функция ExecNotificationQueryWmi (Справочник по неуправляемым API)"
description: "Функция ExecNotificationQueryWmi выполняет запрос для получения событий."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6dd0926d2262f8d0aa125b86755017a65a95a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="execnotificationquerywmi-function"></a>Функция ExecNotificationQueryWmi
Выполняет запрос для получения событий. Вызов возвращается немедленно, а вызывающий объект может выполнять опрос возвращаемый перечислитель для событий по мере их поступления. Освобождение возвращаемый перечислитель отменяет запрос.  

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
[in] Строка с допустимым запросом язык, поддерживаемый управления Windows. Он должен быть «WQL», сокращение для языка запросов WMI.

`strQuery`  
[in] Текст запроса. Этот параметр не может быть `null`.

`lFlags`   
[in] Комбинация из двух следующих флагов, влияющих на поведение этой функции. Эти значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде. 

| Константа | Значение  | Описание:  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Флаг вызывает полусинхронных вызовов. Если этот флаг не установлен, возникнет ошибка. Это так, как будут получены события постоянно, это означает, что пользователь должен опросить возвращаемый перечислитель. Блокирует этот вызов бесконечно делает это невозможно. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Эта функция возвращает только вперед перечислителя. Обычно последовательным перечислители работают быстрее и использовать меньше памяти, чем обычный перечислители, но не разрешать вызовы [клон](clone.md). |

`pCtx`  
[in] Как правило, это значение равно `null`. В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенные события. 

`ppEnum`  
[out] Если ошибок нет, получающей указатель на перечислитель, который позволяет вызывающему объекту получить экземпляры в результирующем наборе запроса. В разделе [примечания](#remarks) Дополнительные сведения.

`authLevel`  
[in] Уровень авторизации.

`impLevel`[in] Уровень олицетворения.

`pCurrentNamespace`   
[in] Указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) , представляющий текущего пространства имен.

`strUser`   
[in] Имя пользователя. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

`strPassword`   
[in] Пароль. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

`strAuthority`   
[in] Имя домена пользователя. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть. |
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | Запрос указывает класс, который не существует. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | Запрошено слишком много точности в доставки событий. Должно быть указано больше погрешность опроса. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | Requess запрос может предоставить больше сведений, чем управления Windows. Это `HRESULT` возвращается, когда запрос приводит к запросу опроса всех объектов в пространстве имен. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Запрос содержит синтаксическую ошибку. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Запрошенный язык запросов не поддерживается. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Запрос слишком сложен. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI был, скорее всего, остановлен и перезапускать. Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | Не удается обработать запрос. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) метод.

После возврата функции, вызывающий объект периодически передает возвращаемый `ppEnum` объект [Далее](next.md) функции, если доступны все события.

Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL. Большое число WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки, что `HRESULT` значение. Предельного количества ключевых слов языка WQL зависит от сложности запроса.

При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
