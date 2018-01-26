---
title: "Функция QualifierSet_GetNames (Справочник по неуправляемым API)"
description: "Функция QualifierSet_GetNames извлекает имена квалификаторов из объекта или свойства."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_GetNames
helpviewer_keywords: QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6077b448c2644f68d12679cf208ee921c2af119a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetgetnames-function"></a>Функция QualifierSet_GetNames
Получает имена всех квалификаторов или определенных квалификаторов, которые доступны из текущего объекта или свойства. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`   
[in] Этот параметр не используется.

`ptr`   
[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.

`lFlags`   
[in] Одно из следующих флагов или значений, определяющее, какие имена включаемых в перечислении.

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возврате только имена квалификаторов текущее свойство или объект. <br/> Для свойства: вернуться только квалификаторами определенные свойства (включая переопределения), а не эти квалификаторы распространены из определения класса. <br/> Для экземпляра: возвращают только имена квалификатор данного экземпляра. <br/> Для класса: вернуться только квалификаторами определенного класса beiong производным.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возвращении только имена квалификаторов распространяются из другого объекта. <br/> Для свойства: возврат распространяются только квалификаторами этому свойству из определения класса, а не из самого свойства. <br/> Для экземпляра: возврат распространяются только те квалификаторы из определения класса. <br/> Для класса: возвращают только те имена квалификатор, наследуемые от родительских классов. |

`pstrNames`[out] Новый `SAFEARRAY` , содержащий запрошенную имена. Массив может иметь 0 элементов. Если возникает ошибка, новый `SAFEARRAY` не возвращается.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Чтобы начать новое перечисление доступен не хватает памяти. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) метод.

После получения имена квалификаторов, к каждой квалификатор по имени путем вызова [QualifierSet_Get](qualifierset-get.md) функции. 

Он не является ошибкой для данного объекта иметь ноль квалификаторы, поэтому число строк в `pstrNames` при возвращении может быть 0, несмотря на то, что функция возвращает `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
