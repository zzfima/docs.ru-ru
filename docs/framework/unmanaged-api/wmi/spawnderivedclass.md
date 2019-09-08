---
title: Функция Спавндериведкласс (Справочник по неуправляемым API)
description: Функция Спавндериведкласс создает новый объект, производный от объекта.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c213f311f1af1e56d0ce24eba3b76f33be541323
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798228"
---
# <a name="spawnderivedclass-function"></a>Функция Спавндериведкласс
Создает объект производного класса из указанного объекта.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`ppNewClass`  
заполняет Получает указатель на новый объект определения класса. При возникновении ошибки новый объект не возвращается и `ppNewClass` остается неизменным. Его значение не может `null`быть.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Запрошена Недопустимая операция, например порождение класса из экземпляра. |
| `WBEM_E_INCOMPLETE_CLASS` | Исходный класс не был полностью определен или зарегистрирован в управлении Windows, поэтому новый производный класс не разрешен. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Свойство `ppNewClass` имеет значение `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: спавндериведкласс](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .

`ptr`должно быть определением класса, который станет родительским классом порожденного объекта. Возвращаемый объект превращается в подкласс текущего объекта.

Новый объект, возвращенный `ppNewClass` в, автоматически станет подклассом текущего объекта. Это поведение не может быть переопределено. Нет других методов, с помощью которых можно создать подклассы (производные классы).

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
