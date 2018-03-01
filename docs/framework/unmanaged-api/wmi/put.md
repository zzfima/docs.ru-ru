---
title: "Поместите функцию (Справочник по неуправляемым API)"
description: "Функция Put присваивает новое значение именованного свойства."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09d3edc74b34688d5cc36e688f634850cfb60910
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="put-function"></a>PUT-функция
Присваивает новое значение именованного свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`wszName`  
[in] Имя свойства. Этот параметр не может быть `null`.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pVal`   
[in] Указатель на допустимый `VARIANT` , становится новым значением свойства. Если `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`, является свойство `null`. 

`vtType`  
[in] Тип `VARIANT` , на который указывает `pVal`. В разделе [примечания](#remarks) Дополнительные сведения.
 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Тип свойства не распознан. Это значение возвращается при создании экземпляров класса, если класс уже существует. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Для экземпляров: Указывает, что `pVal` указывает `VARIANT` неверный тип для свойства. <br/> Для определения классов: свойство уже существует в родительском классе, а новый тип модели COM отличается от старого типа COM. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) метод.

Эта функция всегда перезаписывается текущим значением свойства на новый. Если [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указывает на определения класса, `Put` создает или обновляет значение свойства. Когда [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указывает на экземпляр CIM `Put` обновляет значение свойства. `Put` нельзя создать значение свойства.

`__CLASS` Системы свойство доступно только для записи во время создания класса, когда он может не быть пустым. Все системные свойства доступны только для чтения.

Пользователь не может создавать свойства с именами, начинаться или заканчиваться символом подчеркивания («_»). Данное свойство зарезервировано для системных классов и свойств.

Если свойство задано `Put` функция существует в родительском классе, если тип свойства не соответствует родительского класса типа изменяется значение по умолчанию свойства. Если свойство не существует и не является несоответствие типов, свойство ceated.

Используйте `vtType` параметр только при создании новых свойств в определении класса CIM и `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`. В этом случае `vType` параметр указывает тип CIM свойства. Во всех остальных случаях `vtType` должно быть равно 0. `vtType`также должен быть равен 0, если базовый объект является экземпляром (даже если `Val` — `null`), так как тип свойства является фиксированным и не может быть изменено.   

## <a name="example"></a>Пример

Пример см. в разделе [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
