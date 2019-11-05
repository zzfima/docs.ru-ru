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
ms.openlocfilehash: e7bedcb5c56f9976f8dfd2619081971075d0d809
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127302"
---
# <a name="qualifierset_delete-function"></a>Функция QualifierSet_Delete
Удаляет указанный квалификатор по имени.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`   
окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName`   
окне Имя удаляемого квалификатора.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр `wszName`. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Удаление этого квалификатора недопустимо. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанный квалификатор не найден. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Локальное переопределение удалено, и исходный квалификатор из родительского объекта возобновил область. |

## <a name="remarks"></a>Заметки

Эта функция создает оболочку для вызова метода [ивбемкуалифиерсет::D удалить](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .

Из-за правил распространения квалификаторов определенный квалификатор может быть унаследован от другого объекта и просто переопределен в текущем классе или экземпляре. В этом случае метод `QualifierSet_Delete` сбрасывает квалификатор до исходного наследуемого значения. Функция в этом случае возвращает код состояния `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
