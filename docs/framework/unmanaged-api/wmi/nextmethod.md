---
title: Функция NextMethod (Справочник по неуправляемым API)
description: Функция NextMethod получает следующий метод в перечислении.
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
ms.openlocfilehash: cd4559663194cb845fb0cc040e1f6739e38caa0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pName`  
[out] Указатель, который указывает на `null` до вызова метода. Когда функция возвращает, новый адрес `BSTR` , содержащий имя метода. 

`ppSignatureIn`  
[out] Указатель, получающий указатель [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) , содержащий `in` параметры для метода. 

`ppSignatureOut`  
[out] Указатель, получающий указатель [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) , содержащий `out` параметры для метода. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Был не вызов [ `BeginEnumeration` ](beginenumeration.md) функции. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Нет дополнительных свойств в перечислении. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) метод.

Вызывающий объект начинается последовательность перечисления путем вызова метода [BeginMethodEnumeration](beginmethodenumeration.md) функции, а затем вызывает функцию [NextMethod] до возврата функции `WBEM_S_NO_MORE_DATA`. При необходимости, вызывающий объект завершения последовательности путем вызова [EndMethodEnumeration](endmethodenumeration.md). Вызывающий объект может завершить перечисление раньше путем вызова [EndMethodEnumeration](endmethodenumeration.md) в любое время.

## <a name="example"></a>Пример

Пример C++ см. в разделе [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
