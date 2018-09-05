---
title: Функция QualifierSet_GetNames (Справочник по неуправляемым API)
description: Функция QualifierSet_GetNames извлекает имена квалификаторы из объекта или свойства.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84059c5e5542e13b1d4fc4efcfc4c7f418db391e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672126"
---
# <a name="qualifiersetgetnames-function"></a>Функция QualifierSet_GetNames
Возвращает имена всех квалификаторов или определенных квалификаторов, доступные из текущего объекта или свойства. 

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
[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.

`lFlags`   
[in] Одно из следующих значений, определяющих, какие имена, чтобы включить в перечисление или флаги.

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возвращать только имена квалификаторы объекту или текущего свойства. <br/> Для свойства: возвращать только квалификаторы конкретных свойству (включая переопределения), а не эти квалификаторы распространены из определения класса. <br/> Для экземпляра: возвращает только квалификатор с определенным экземпляром имена. <br/> Для класса: вернуться только квалификаторы конкретного класса beiong производным.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возврат только имена квалификаторы распространяются из другого объекта. <br/> Для свойства: возврат распространяются только квалификаторы к этому свойству из определения класса, а не из самого свойства. <br/> Для экземпляра: возврат только эти квалификаторы распространяются из определения класса. <br/> Для класса: возвращают только те имена квалификатор, наследуемые от родительских классов. |

`pstrNames` [out] Новый `SAFEARRAY` , содержащий запрошенную имена. Массив может иметь 0 элементов. Если возникает ошибка, новый `SAFEARRAY` не возвращается.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти, позволяющих начать новое перечисление. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) метод.

После получения имена квалификатор, каждый префикс доступен по имени путем вызова [QualifierSet_Get](qualifierset-get.md) функции. 

Это не ошибка для данного объекта иметь нуль квалификаторы, поэтому число строк в `pstrNames` при возврате может быть равен 0, несмотря на то, что функция возвращает `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
