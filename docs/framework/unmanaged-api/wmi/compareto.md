---
title: "Функции CompareTo (Справочник по неуправляемым API)"
description: "Функции CompareTo сравнивает объект с другим объектом WMI."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 038074b5bb3adc816caa226d3167395758d2ae57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="compareto-function"></a>Функции CompareTo
Сравнивает объект с другим объектом управления Windows.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`flags`  
[in] Побитовое сочетание флагов, указывающих характеристики объектов, которые можно использовать при сравнении. В разделе [примечания](#remarks) Дополнительные сведения.

`pCompareTo`  

[in] Объект для сравнения. `pcompareTo`должен быть допустимым [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра; не может быть `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `BeginEnumeration` была произведена без промежуточных вызовов [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Объекты различаются. |
| `WBEM_S_SAME` | 0 | Объекты одинаковы основании флаги сравнения. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) метод.

Флаги, которые могут быть переданы как `lEnumFlags` аргумент определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде. Можно указать отдельные характеристики, участвующих в сравнении, указав побитовое сочетание следующих флагов:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Игнорируйте источника (сервера и пространства имен, из которых они происходят). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Игнорировать все квалификаторы (включая **ключ** и **динамическое**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Игнорировать значения свойств по умолчанию. Этот флаг применяется только для сравнения классов. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Пропуск квалификаторов. Этот флаг по-прежнему учитывает квалификаторы, но игнорирует такие правила распространения и ограничения. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Не учитывать регистр при сравнении строковых значений. Это относится как к строкам и значения квалификатора. Сравнение имен свойств и квалификаторов всегда выполняется с учетом регистра, независимо от того, является ли этот флаг установлен. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Предположим, что сравниваемые объекты являются экземпляров того же класса. Следовательно этот флаг сравнивает только сведения, относящиеся к экземпляру. Используйте этот флаги для оптимизации производительности. Если объекты не из того же класса, результаты не определены. |

Или можно указать один составной флаг следующим образом:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Учитывать все характеристики в сравнении. |

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
