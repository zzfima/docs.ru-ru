---
title: Функция SpawnInstance (Справочник по неуправляемым API)
description: Функция SpawnInstance создает новый экземпляр класса.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97a3ab62cda82526a7ad8b8e5d985d9fce7d6f07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783075"
---
# <a name="spawninstance-function"></a>Функция SpawnInstance
Создает экземпляр класса.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`ppNewInstance`  
[out] Получает указатель на новый экземпляр класса. Если возникает ошибка, объект не возвращается, и `ppNewInstance` слева без изменений.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` не является допустимым определением класса и не может создавать новые экземпляры. Он не полон, либо он не был зарегистрирован с помощью службы управления Windows, вызвав [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Свойство `ppNewClass` имеет значение `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) метод.

`ptr` Определение класса приобретаются у управления Windows. (Обратите внимание, что порождает экземпляра из экземпляра поддерживается, но возвращаемый экземпляр является пустым.) Затем можно использовать это определение класса для создания новых экземпляров. Вызов [PutInstanceWmi](putinstancewmi.md) функции является обязательным, если вы собираетесь записать экземпляр для управления Windows.

Новый объект, возвращаемый в `ppNewClass` автоматически становится подкласс текущего объекта. Не удается переопределить это поведение. Нет никакой другой метод, по которой можно создавать подклассы (производные классы).

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
