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
ms.openlocfilehash: 81f4d5219865bf7f7c9e6d284d74d0c249729dfc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194426"
---
# <a name="spawnderivedclass-function"></a>Функция SpawnDerivedClass
Создает объект производного класса из указанного объекта.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
