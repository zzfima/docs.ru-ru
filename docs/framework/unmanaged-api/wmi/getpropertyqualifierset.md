---
title: Функция GetPropertyQualifierSet (Справочник по неуправляемым API)
description: Функция GetPropertyQualifierSet получает квалификатор устанавливаемое для свойства.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcddca2e435a3f5bf4b8d083784613254d9801a4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786184"
---
# <a name="getpropertyqualifierset-function"></a>Функция GetPropertyQualifierSet
Получает набор квалификаторов для определенного свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszMethod`  
[in] Имя свойства. `wszProperty` должен указывать на допустимый `LPCWSTR`. 

`ppQualSet`  
[out] Получает указатель интерфейса, обеспечивающий доступ к квалификаторы свойства. Параметр `ppQualSet` не может иметь значение `null`. Если возникает ошибка, не возвращается новый объект и указатель имеет значение для указания `null`. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Указанный метод не существует. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр — `null`. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | Функция пытается получить квалификаторы для системного свойства. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) метод. 

Вызов этой функции поддерживается только в том случае, если текущий объект является определение класса CIM. Метод манипуляции не доступен для [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters, указывают на экземпляры CIM.

Так как каждый метод может иметь свой собственный квалификаторы [IWbemQualifierSet указатель](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающему объекту добавить, изменить или удалить эти квалификаторы.

Поскольку системные свойства без квалификаторов, функция возвращает `WBEM_E_SYSTEM_PROPERTY` при попытке получить [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) указатель для системного свойства.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
