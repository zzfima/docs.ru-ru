---
title: Функция NextMethod (Неуправляемая ссылка API)
description: Функция NextMethod извлекает следующий метод в перечислении.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174931"
---
# <a name="nextmethod-function"></a>Функция NextMethod
Извлекает следующий метод в перечислении, который начинается с вызова [beginMethodEnumeration.](beginmethodenumeration.md)  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pName`  
(ваут) Указатель, который `null` указывает на до вызова. Когда функция возвращается, адрес `BSTR` нового, который содержит имя метода.

`ppSignatureIn`  
(ваут) Указатель, который получает указатель на [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) содержащий `in` параметры для метода.

`ppSignatureOut`  
(ваут) Указатель, который получает указатель на [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) содержащий `out` параметры для метода.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Не было никакого [`BeginEnumeration`](beginenumeration.md) вызова к функции. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении больше нет свойств. |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::NextMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)

Вызывающий абонент начинает последовательность перечисления, вызывая функцию [BeginMethodEnumeration,](beginmethodenumeration.md) а затем вызывает `WBEM_S_NO_MORE_DATA`функцию «NextMethod» до тех пор, пока функция не вернется. Дополнительно абонент завершает последовательность, позвонив [в EndMethodEnumeration.](endmethodenumeration.md) Звонящее может досрочно завершить перечисление, позвонив в [EndMethodEnumeration](endmethodenumeration.md) в любое время.

## <a name="example"></a>Пример

На примере СЗ см. [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
