---
title: Функция CreateClassEnumWmi (Справочник по неуправляемым API)
description: Функция CreateClassEnumWmi Возвращает перечислитель для всех классов, которые удовлетворяют заданным условиям.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fc8b25465657ba41220d4a19e10aa06b0e30e86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733042"
---
# <a name="createclassenumwmi-function"></a>CreateClassEnumWmi function
Возвращает перечислитель для всех классов, которые удовлетворяют указанным критериям выбора.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

`strSuperclass`    
[in] В противном случае `null` или пусто, имя класса-родителя; перечислитель возвращает только подклассы этого класса. Если это `null` либо оставьте пустым и `lFlags` является WBEM_FLAG_SHALLOW, возвращает только верхнего уровня классов (классов без родительского класса). Если это `null` либо оставьте пустым и `lFlags` является `WBEM_FLAG_DEEP`, возвращаются все классы в пространстве имен.

`lFlags`   
[in] Сочетание флагов, влияющих на поведение этой функции. Следующие значения определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде: 

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Если набор, функция извлекает измененные квалификаторы, хранящиеся в локализованных имен языкового стандарта текущего соединения. <br/> В противном случае набор, функция получает только квалификаторы, хранящихся в пространство имен немедленно. |
| `WBEM_FLAG_DEEP` | 0 | Перечисление включает всех подклассов в иерархии, но не для этого класса. |
| `WBEM_FLAG_SHALLOW` | 1 | Перечисление содержит только чистые экземпляры этого класса и исключает все экземпляры из подклассов, которые предоставляют свойства, не найден в этом классе. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Этот флаг приводит к Полусинхронный вызов. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Функция возвращает только вперед перечислителя. Обычно перечислители только вперед, выполняются быстрее и использовать меньше памяти, чем обычные перечислители, но они не допускают вызовы [клона](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI сохраняет указатели на объекты в enumration до их появления. | 

Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.

`pCtx`  
[in] Как правило, это значение равно `null`. В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы. 

`ppEnum`  
[out] Получает указатель на перечислитель.

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
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strSuperClass` — не существует. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI был, вероятно, остановлена или перезапустить. Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) метод.

Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также
- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
