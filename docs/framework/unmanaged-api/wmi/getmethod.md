---
title: Функция GetMethod (Справочник по неуправляемым API)
description: Функция GetMethod получает сведения о методе.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65b8cb74a028892a3494e818f2b523f75e8766a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getmethod-function"></a>GetMethod-функция
Возвращает сведения об указанном методе.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`wszName`  
[in] Имя метода. Этот параметр не может быть `null` и должен указывать на допустимый `LPCWSTR`.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`ppInSignature`   
[out] Указатель на адрес [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) , описывающий в paramteers к методу экземпляра. Этот параметр учитывается, если задано значение `null`. 

`ppOutSignature`  
[out] Указатель на адрес [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляр, описывающий выходные параметры метода. Этот параметр учитывается, если задано значение `null`. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не найдено. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) метод.

Можно установить Windows Management [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указатель `null` Если метод имеет входные параметры нет.

В `ppInSignature` и `ppOutSignature` описывают входные и выходные параметры, соответственно, как свойства в `IWbemClassObject` экземпляр класса системы [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx). Свойства в `ppInsignature` именуются **Param *** n*, где *n* позиция параметра в сигнатуре метода (например, `Param1`, `Param2`и т. д.). Свойства в `ppOutSignature` также называются **Param *** n*, а возвращаемое значение совпадает с именем **ReturnValue**. Дополнительные сведения и пример см. в разделе [IWbemClassObject::GetMethod метод](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).

## <a name="requirements"></a>Требования  
**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
