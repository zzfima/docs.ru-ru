---
title: Функция SpawnDerivedClass (Справочник по неуправляемым API)
description: Функция SpawnDerivedClass создает новый объект, который является производным от объекта.
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
ms.openlocfilehash: 6f05f349699b28262c1628cadc6e9a0fb0a3459c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783103"
---
# <a name="spawnderivedclass-function"></a>Функция SpawnDerivedClass
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
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`ppNewClass`  
[out] Получает указатель на новый объект определения класса. Если возникает ошибка, объект не возвращается, и `ppNewClass` слева без изменений. Его значение не может быть `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Запрошена недопустимая операция, например порождение класса от экземпляра. |
| `WBEM_E_INCOMPLETE_CLASS` | Исходный класс был не полностью определенных или зарегистрированы с помощью службы управления Windows, поэтому новый производный класс не допускается. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Свойство `ppNewClass` имеет значение `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) метод.

`ptr` должно быть определение класса, который становится родительским классом для порожденного объекта. Возвращаемый объект становится подкласс текущего объекта.

Новый объект, возвращаемый в `ppNewClass` автоматически становится подкласс текущего объекта. Не удается переопределить это поведение. Нет никакой другой метод, по которой можно создавать подклассы (производные классы).

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
