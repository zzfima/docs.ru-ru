---
title: "Функция QualifierSet_BeginEnumeration (Справочник по неуправляемым API)"
description: "Функция QualifierSet_BeginEnumeration Сбрасывает перечислитель квалификаторы объекта."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_BeginEnumeration
helpviewer_keywords: QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 440dde03f4ed138a33eb6f817723d7c5c74f6d46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetbeginenumeration-function"></a>Функция QualifierSet_BeginEnumeration
Возвращает перечислитель квалификаторы объект в начало перечисления.  

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
[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.

`lFlags`   
[in] Побитовое сочетание флагов или значений, описанных в [примечания](#remarks) раздел, который указывает квалификаторы для включения в перечислении.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lFlags` Недопустимый параметр. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `QualifierSet_BeginEnumeration` была произведена без промежуточных вызовов [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Чтобы начать новое перечисление доступен не хватает памяти. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) метод.

Для перечисления всех квалификаторов для объекта, этот метод должен вызываться до первого вызова [QualifierSet_Next](qualifierset-next.md). Гарантируется, что порядок, в котором перечислены квалификаторы является инвариантным для данного перечисления.

Флаги, которые могут быть переданы как `lEnumFlags` аргумент определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде.   

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возврате только имена квалификаторов текущее свойство или объект. <br/> Для свойства: вернуться только квалификаторами определенные свойства (включая переопределения), а не эти квалификаторы распространены из определения класса. <br/> Для экземпляра: возвращают только имена квалификатор данного экземпляра. <br/> Для класса: вернуться только квалификаторами определенного класса beiong производным.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возвращении только имена квалификаторов распространяются из другого объекта. <br/> Для свойства: возврат распространяются только квалификаторами этому свойству из определения класса, а не из самого свойства. <br/> Для экземпляра: возврат распространяются только те квалификаторы из определения класса. <br/> Для класса: возвращают только те имена квалификатор, наследуемые от родительских классов. |

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
