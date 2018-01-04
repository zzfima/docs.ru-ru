---
title: "Функция BeginEnumeration (Справочник по неуправляемым API)"
description: "Функция BeginEnumeration устанавливает перечислитель в начало перечисления"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90c3e8448a61145290ea4a75b1d38f7ae010cb9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a>Функция BeginEnumeration
Сбрасывает перечислитель в начало перечисления.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`lEnumFlags`  
[in] Побитовое сочетание флагов или значений, описанных в [примечания](#remarks) раздел, который управляет свойствами, которые включены в перечисление.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Сочетание флагов в `lEnumFlags` недопустим или недопустимый аргумент был указан. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `BeginEnumeration` была произведена без промежуточных вызовов [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Чтобы начать новое перечисление доступен не хватает памяти. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) метод.

Флаги, которые могут быть переданы как `lEnumFlags` аргумент определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде.  Можно объединить один флаг из каждой группы с любого флага из другой группы. Однако флаги из той же группы являются взаимоисключающими. 

**Группа 1**

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Включает свойства, составляющие только ключ. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Включают свойства, которые являются только ссылки на объекты. |

**Группа 2**

Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Ограничьте к только системные свойства перечисления. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Включает локальные и распространяемые свойства, но исключает системные свойства из перечисления. |

Для классов:

Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Ограничения перечисления для свойства при переопределении в определении класса. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Ограничения перечисления для свойства при переопределении в текущем определении класса и новые свойства, определенные в классе. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Значение маски (а не флаг) для применения к `lEnumFlags` значение для проверки, если параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` имеет значение. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничения перечисления для свойства, которые были определены или изменены в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничения перечисления для свойства, наследуемые из базовых классов. |

Для экземпляров:

Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничения перечисления для свойства, которые были определены или изменены в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничения перечисления для свойства, наследуемые из базовых классов. |


## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
