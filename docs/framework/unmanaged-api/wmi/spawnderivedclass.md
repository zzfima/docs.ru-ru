---
title: Функция SpawnDerivedClass (Неуправляемая справка API)
description: Функция SpawnDerivedClass создает новый объект, который происходит от объекта.
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
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174853"
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
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`ppNewClass`  
(ваут) Получает указатель на новый объект определения класса. При возникновении ошибки новый объект `ppNewClass` не возвращается и остается неизмененным. Его ценность `null`не может быть .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Была запрошена недействительная операция, например, нерест класса из экземпляра. |
| `WBEM_E_INCOMPLETE_CLASS` | Класс исходного кода не был полностью определен или зарегистрирован в Windows Management, поэтому новый класс производных не допускается. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для выполнения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр `ppNewClass` равен `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::SpawnDerivedClass.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)

`ptr`должно быть определение класса, которое становится родительским классом нерестимого объекта. Возвращаемый объект становится подклассом текущего объекта.

Новый объект, `ppNewClass` возвращенный в автоматически становится подклассом текущего объекта. Такое поведение нельзя переопределить. Нет другого метода, с помощью которого могут быть созданы подклассы (производные классы).

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
