---
title: Удалить функцию (Справочник по неуправляемым API)
description: Функция удаления удаляет указанное свойство и все его квалификаторы из определения класса CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 791e75aa60fd651dde1555339e31664a3523e1eb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554391"
---
# <a name="delete-function"></a>Удаление функции
Удаляет указанное свойство и все его квалификаторы из определения класса CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszName`  
[in] Имя свойства для удаления. `wszName` должен быть указателем на допустимый `LPCWSTR`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Не удается удалить свойство. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszzName` недопустим. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не существует. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти для завершения операции. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | Свойство наследуется от базового класса. |
| `WBEM_E_SYSTEM_PROPERTY` | | Свойство является страницей системных свойств. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | Функция удалить значение override по умолчанию для текущего класса. Значение по умолчанию для этого свойства в родительском классе уже reactiviated. | 

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
