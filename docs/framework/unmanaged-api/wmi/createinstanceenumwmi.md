---
title: "Функция CreateInstanceEnumWmi (Справочник по неуправляемым API)"
description: "Функция CreateInstanceEnumWmi Возвращает перечислитель, содержащий экземпляры указанного класса, соответствующие условиям выбора."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateInstanceEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateInstanceEnumWmi
helpviewer_keywords: CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19a4102796da7a5692eb5b9b459a6a95ff7409f9
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="createinstanceenumwmi-function"></a>Функция CreateInstanceEnumWmi
Возвращает перечислитель, который возвращает экземпляры указанного класса, удовлетворяющих указанные критерии выбора. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
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

`strFilter`    
[in] Имя класса, для которого требуются экземпляров. Этот параметр не может быть `null`.

`lFlags`   
[in] Сочетание флагов, влияющих на поведение этой функции. Следующие значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде: 

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Если набор, функция возвращает изменяемые квалификаторы, хранимых в локализованных имен языкового стандарта текущего соединения. <br/> В противном случае набор, функция возвращает только квалификаторы, хранимых в интерпретации имен. |
| `WBEM_FLAG_DEEP` | 0 | Перечисление включает это и всех подклассов в иерархии. |
| `WBEM_FLAG_SHALLOW` | 1 | Перечисление содержит только чистые экземпляры этого класса и исключает все экземпляры подклассов, которые предоставляют свойства, не найденные в этом классе. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Флаг вызывает полусинхронных вызовов. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Эта функция возвращает только вперед перечислителя. Обычно последовательным перечислители работают быстрее и использовать меньше памяти, чем обычный перечислители, но не разрешать вызовы [клон](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI сохраняет указатели на объекты в enumration до их появления. | 

Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.

`pCtx`  
[in] Как правило, это значение равно `null`. В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного экземпляра.

`ppEnum`  
[out] Получает указатель на перечислитель.

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

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Пользователь не имеет разрешения на просмотр экземпляров указанного класса. |
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strFilter` — не существует. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI был, скорее всего, остановлен и перезапускать. Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) метод.

Обратите внимание, что возвращаемый перечислитель может иметь ноль элементов.

При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
