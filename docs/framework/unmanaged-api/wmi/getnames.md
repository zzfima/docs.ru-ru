---
title: Функция GetNames (Справочник по неуправляемым API)
description: Функция GetNames получает имена свойств объекта.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53174bf060938d5a55cbd196944ac11916d59cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661398"
---
# <a name="getnames-function"></a>Функция GetNames
Получает подмножество имен или все имена свойств объекта. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszQualifierName`  
[in] Указатель на допустимую `LPCWSTR` , задающий имя квалификатора, которое работает как часть фильтра. Дополнительные сведения см. в разделе ["Примечания"](#remarks) раздел. Этот параметр может иметь значение `null`. 

`lFlags`  
[in] Сочетание битовых полей. Дополнительные сведения см. в разделе ["Примечания"](#remarks) раздел.

`pQualifierValue`   
[in] Указатель на допустимую `VARIANT` структуру, инициализированную со значением фильтра. Этот параметр может иметь значение `null`. 

`pstrNames`  
[out] Объект `SAFEARRAY` структуру, которая содержит имена свойств. На запись в этот параметр всегда должен быть указателем на `null`. См. в разделе ["Примечания"](#remarks) Дополнительные сведения. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы, или указано неверное сочетание флагов и параметры. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) метод.

Именованных возвращаемых контролируются с помощью сочетания флагов и параметры. Например функция может вернуть имена всех свойств или только имена ключевых свойств.  Основным фильтром указывается в `lFlags` параметра и другие параметры зависят от его.

Флаг значения в `lFlags` являются битовые поля


Флаги, которые могут передаваться как `lEnumFlags` аргумента находятся в битовых полей, которые определены в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.  Вы можете объединить один флаг из каждой группы с любой флаг из другой группы. Однако флаги из одной группы являются взаимоисключающими. 

| Флаги группы 1 |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Возвращает имена всех свойств. `strQualifierName` и `pQualifierVal` не используются. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Возвращать только свойства, которые имеют квалификатор именем, указанным `strQualifierName` параметра. Если этот флаг используется, необходимо указать `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Возвращать только свойства, которые не имеют квалификатор именем, указанным `strQualifierName` параметра. Если этот флаг используется, необходимо указать `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Возвращать только те свойства, которые имеют квалификатор именем, указанным `wszQualifierName` параметр и также имеют значения, идентичны данным, определяемое `pQualifierVal` структуры. Если этот флаг используется, необходимо указать и `wszQualifierName` и `pQualifierValue`. |

| Флаги группы 2 |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Возвращать только имена свойств, определяющих ключи. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Возвращаемое только имена свойств, которые являются ссылками на объект. |

| Группа 3 флаги |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возвращать только имена свойств, которые принадлежат к наиболее производный класс. Исключите свойства родительского класса. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Возвращать только имена свойств, принадлежащих родительских классов. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Возвращать только имена системных свойств. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Возвращать только имена несистемных свойств. |

Функция всегда выделяет новый `SAFEARRAY` при его использовании возвращается `WBEM_S_NO_ERROR`, и `pstrNames` всегда имеет значение указывать на него. Возвращаемый массив может иметь 0 элементов, если нет свойств, соответствующих заданным фильтрам. Если функция возвращает значение, отличное от `WBM_S_NO_ERROR`, новый `SAFEARRAY` структуры не возвращается.
 
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
