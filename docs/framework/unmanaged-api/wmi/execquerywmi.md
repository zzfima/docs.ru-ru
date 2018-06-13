---
title: Функция ExecQueryWmi (Справочник по неуправляемым API)
description: Функция ExecQueryWmi выполняет запрос для получения объектов.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b482f2ca2e2d5c06e69945adb71aa6c0f5d26465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462095"
---
# <a name="execquerywmi-function"></a>Функция ExecQueryWmi
Выполняет запрос для получения объектов.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ExecQueryWmi (
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
[in] Сочетание флагов, влияющих на поведение этой функции. Следующие значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде: 

| Константа | Значение  | Описание  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Если набор, функция возвращает изменяемые квалификаторы, хранимых в локализованных имен языкового стандарта текущего соединения. <br/> В противном случае набор, функция возвращает только квалификаторы, хранимых в интерпретации имен. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Флаг вызывает полусинхронных вызовов. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Эта функция возвращает только вперед перечислителя. Обычно последовательным перечислители работают быстрее и использовать меньше памяти, чем обычный перечислители, но не разрешать вызовы [клон](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI сохраняет указатели на объекты в enumration до их появления. | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | Обеспечивает все возвращаемые объекты имели достаточно сведений в них так, системные свойства, такие как **__PATH**, **__RELPATH**, и **__SERVER**, не являются `null`. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Этот флаг используется для создания прототипов. Он не выполняет запрос и возвращает объект, который выглядит как типичный результирующий объект. |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | Причины прямой доступ к поставщику для класса, указанного независимо от его родительского класса и его подклассов. |

Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.

`pCtx`  
[in] Как правило, это значение равно `null`. В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы. 

`ppEnum`  
[out] Если ошибок нет, получающей указатель на перечислитель, который позволяет вызывающему объекту получить экземпляры в результирующем наборе запроса. Запрос может содержать результирующий набор с нуля экземпляров. В разделе [примечания](#remarks) Дополнительные сведения.

`authLevel`  
[in] Уровень авторизации.

`impLevel` [in] Уровень олицетворения.

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

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть. |
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Запрос содержит синтаксическую ошибку. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Запрошенный язык запросов не поддерживается. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Запрос слишком сложен. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI был, скорее всего, остановлен и перезапускать. Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Запрос указывает класс, который не существует. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) метод.

Эта функция обрабатывает запрос, указанный в `strQuery` параметр и создает перечислитель, через который вызывающий объект может получить доступ к результаты запроса. Перечислитель является указателем на [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) интерфейса; запроса результаты являются экземплярами класса объектов, доступны через [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) интерфейса.

Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL. Большое число WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки, что `HRESULT` значение. Предельного количества ключевых слов языка WQL зависит от сложности запроса.

При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
