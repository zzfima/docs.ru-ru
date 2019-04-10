---
title: Функция BeginEnumeration (Справочник по неуправляемым API)
description: Функция BeginEnumeration устанавливает перечислитель в начало перечисления
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212301"
---
# <a name="beginenumeration-function"></a>Функция BeginEnumeration
Сбрасывает перечислитель на начало перечисления.  

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

`vFunc`\
[in] Этот параметр не используется.

`ptr`\
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`lEnumFlags`\
[in] Побитовое сочетание флагов или значения, описанные в ["Примечания"](#remarks) раздел, который управляет свойствами включена в перечисление.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Комбинация флагов в `lEnumFlags` недопустим или указан недопустимый аргумент был указан. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `BeginEnumeration` была сделана без промежуточных вызовов к [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти, позволяющих начать новое перечисление. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) метод.

Флаги, которые могут передаваться как `lEnumFlags` аргумент определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.  Вы можете объединить один флаг из каждой группы с любой флаг из другой группы. Однако флаги из одной группы являются взаимоисключающими. 

**Группа 1**

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Включают свойства, которые составляют только ключ. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Включают свойства, которые являются только ссылки на объекты. |

**Группа 2**

Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Ограничения перечисления только системные свойства. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Включает локальные и распространенных свойств, но исключает системные свойства из перечисления. |

Для классов:

Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Ограничения перечисления для свойства при переопределении в определении класса. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Ограничения перечисления для свойства, переопределить в определении текущего класса и новые свойства, определенные в классе. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Объект маскировать (а не флаг) для применения к `lEnumFlags` значение для проверки, если параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` имеет значение. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничения перечисления для свойства, которые определены или являются изменения в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничения перечисления для свойства, наследуемые от базовых классов. |

Для экземпляров:

Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничения перечисления для свойства, которые определены или являются изменения в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничения перечисления для свойства, наследуемые от базовых классов. |

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)