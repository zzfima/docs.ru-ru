---
title: Функция NextMethod (Справочник по неуправляемым API)
description: Функция NextMethod получает следующий метод в перечисление.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d019c67849197cd24171ff607e60e9f08d5ff70
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43451627"
---
# <a name="nextmethod-function"></a>Функция NextMethod
Извлекает следующий метод в перечисление, которое начинается с вызова [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pName`  
[out] Указатель на `null` до вызова метода. Если функция возвращает, новый адрес `BSTR` , содержащий имя метода. 

`ppSignatureIn`  
[out] Указатель, получающий указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `in` параметры метода. 

`ppSignatureOut`  
[out] Указатель, получающий указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `out` параметры метода. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Возникла не вызывался метод [ `BeginEnumeration` ](beginenumeration.md) функции. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Нет дополнительных свойств в перечислении. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) метод.

Вызывающий объект начинается последовательность перечисления путем вызова метода [BeginMethodEnumeration](beginmethodenumeration.md) функции, а затем вызывает функцию [NextMethod] до возврата функции `WBEM_S_NO_MORE_DATA`. При необходимости, вызывающий объект завершает последовательность путем вызова [EndMethodEnumeration](endmethodenumeration.md). Вызывающая сторона может завершить перечисление раньше, вызвав [EndMethodEnumeration](endmethodenumeration.md) в любое время.

## <a name="example"></a>Пример

Пример C++, см. в разделе [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
