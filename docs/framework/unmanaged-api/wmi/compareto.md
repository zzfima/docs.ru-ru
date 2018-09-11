---
title: Функция CompareTo (Справочник по неуправляемым API)
description: Функция CompareTo сравнивает объект с другим объектом WMI.
ms.date: 11/06/2017
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
ms.openlocfilehash: bde25ae7455dd7fe35fe1a0a43bb2a6b560c0e3e
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353308"
---
# <a name="compareto-function"></a>Функция CompareTo
Сравнивает объект с другим объектом управления Windows.  

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
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`flags`  
[in] Побитовое сочетание флагов, определяющих характеристики объектов, которые следует учитывать для сравнения. См. в разделе ["Примечания"](#remarks) Дополнительные сведения.

`pCompareTo`  

[in] Объект для сравнения. `pcompareTo` должен быть допустимым [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра; не может быть `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `BeginEnumeration` была сделана без промежуточных вызовов к [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Объекты различаются. |
| `WBEM_S_SAME` | 0 | Объекты одинаковы основании флаги сравнения. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) метод.

Флаги, которые могут передаваться как `lEnumFlags` аргумент определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде. Можно указать отдельные характеристики, участвующих в сравнении, указав побитовое сочетание флагов:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Не учитывать источник (сервер и пространство имен, которое они поступили). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Игнорировать все квалификаторы (включая **ключ** и **динамическое**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Игнорировать значения свойств по умолчанию. Этот флаг применяется только к сравнения классов. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Игнорируйте квалификаторов. Этот флаг по-прежнему учитывает квалификаторы, но игнорирует такие правила распространения и ограничения. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Не учитывать регистр при сравнении строковых значений. Это относится как к строкам и значения квалификатора. Сравнение имен свойств и квалификаторов всегда выполняется с учетом регистра, независимо от того, является ли этот флаг установлен. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Предположим, что сравниваемые объекты являются экземпляров того же класса. Следовательно этот флаг сравнивает только сведения, относящиеся к экземпляру. Используйте это флаги для оптимизации производительности. Если объекты не имеют одного класса, результаты будут неопределенными. |

Или одного составного флага можно указать следующим образом:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Учитывать все характеристики в сравнении. |

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
