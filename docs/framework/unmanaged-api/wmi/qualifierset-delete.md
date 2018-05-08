---
title: Функция QualifierSet_Delete (Справочник по неуправляемым API)
description: Функция QualifierSet_Delete удаляет квалификатор по имени.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e96ba458edfe7261fd5857b7bcb8486f4a6636
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="qualifiersetdelete-function"></a>Функция QualifierSet_Delete
Удаляет указанный квалификатор по имени.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`   
[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.

`wszName`   
[in] Имя квалификатора, которое необходимо удалить.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` Недопустимый параметр. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Удаление этого квалификатор, недопустимо. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Не найден указанный квалификатор. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Переопределение локальной был удален и исходный квалификатор из родительского объекта возобновил области. |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) метод.

Из-за правила распространения квалификатор квалификатор определенного может были наследуется от другого объекта и просто переопределен в текущего класса или экземпляра. В этом случае `QualifierSet_Delete` метод сбрасывает квалификатор наследуемые исходное значение. В этом случае, функция возвращает код состояния `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
