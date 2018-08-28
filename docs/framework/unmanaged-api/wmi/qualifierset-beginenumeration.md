---
title: Функция QualifierSet_BeginEnumeration (Справочник по неуправляемым API)
description: Функция QualifierSet_BeginEnumeration Сбрасывает перечислитель квалификаторов объекта.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d20701237501834c611c4e498c39597cf275176
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001467"
---
# <a name="qualifiersetbeginenumeration-function"></a>Функция QualifierSet_BeginEnumeration
Сбрасывает перечислитель квалификаторов объекта в начало перечисления.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`   
[in] Этот параметр не используется.

`ptr`   
[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.

`lFlags`   
[in] Побитовое сочетание флагов или значения, описанные в ["Примечания"](#remarks) раздел, в котором указывает квалификаторы для включения в перечислении.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lFlags` Недопустимый параметр. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `QualifierSet_BeginEnumeration` была сделана без промежуточных вызовов к [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти, позволяющих начать новое перечисление. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) метод.

Чтобы перечислить все квалификаторы для объекта, этот метод должен вызываться перед первым вызовом [QualifierSet_Next](qualifierset-next.md). Порядок, в котором перечислены квалификаторы гарантированно инвариантным для данного перечисления.

Флаги, которые могут передаваться как `lEnumFlags` аргумент определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.   

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возвращать только имена квалификаторы объекту или текущего свойства. <br/> Для свойства: возвращать только квалификаторы конкретных свойству (включая переопределения), а не эти квалификаторы распространены из определения класса. <br/> Для экземпляра: возвращает только квалификатор с определенным экземпляром имена. <br/> Для класса: вернуться только квалификаторы конкретного класса beiong производным.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возврат только имена квалификаторы распространяются из другого объекта. <br/> Для свойства: возврат распространяются только квалификаторы к этому свойству из определения класса, а не из самого свойства. <br/> Для экземпляра: возврат только эти квалификаторы распространяются из определения класса. <br/> Для класса: возвращают только те имена квалификатор, наследуемые от родительских классов. |

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
