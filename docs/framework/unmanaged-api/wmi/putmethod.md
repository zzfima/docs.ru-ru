---
title: Функция PutMethod (Неуправляемая ссылка API)
description: Функция PutMethod создает метод.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174918"
---
# <a name="putmethod-function"></a>Функция PutMethod
Создает метод.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`  
(в) Название метода для создания.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pSignatureIn`  
(в) Указатель на копию [класса __Parameters системы,](/windows/desktop/WmiSdk/--parameters) содержащий `in` параметры для метода. Этот параметр игнорируется, `null`если установлен на .  

`pSignatureOut`  
(в)  Указатель на копию [класса __Parameters системы,](/windows/desktop/WmiSdk/--parameters) содержащий `out` параметры для метода. Этот параметр игнорируется, `null`если установлен на .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недействительны. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Параметр `[in, out]` метода, указанный как в объектах *pInSignature,* так и *pOutSignature,* имеет различные квалификаторы.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Параметр метода отсутствует спецификация квалификатора **id.** |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Серия идентификаторов, присвоенная параметрам метода, не является последовательной или не начинается с 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Значение возврата для метода имеет квалификатор **идентификатора.** |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Была предпринята попытка повторного использования существующего имени метода из родительского класса, и подписи не совпадают. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным. |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::PutMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)

Этот вызов метода `ptr` поддерживается только в том случае, если это определение класса CIM. Манипуляция методом недоступна в указателях [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) которые указывают на экземпляры CIM.

Пользователи не могут создавать методы с именами, которые начинаются или заканчиваются с подчеркивания. Это зарезервировано для системных классов и свойств.

Для метода `in` и `out` параметры описываются как свойства в объектах [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

Параметр `[in/out]` может быть определен путем добавления одного `pInSignature` `pOutSignature` и того же свойства к обоим объектам, указанным по параметрам. В этом случае свойства имеют одно и то же значение квалификатора **id.**

Каждое свойство в [объекте __Parameters](/windows/desktop/WmiSdk/--parameters) класса, кроме `ReturnValue` обязательного, имеет квалификатор **идентификатора,** нулевое числовое значение, которое определяет порядок, в котором отображаются параметры. Нет двух параметров может иметь то же значение **id,** и значение **идентификатора** не может быть пропущено. При возникновении одного `PutMethod` из `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`условий функция возвращается.

## <a name="example"></a>Пример

Например, см. метод [IWbemClassObject::PutMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
