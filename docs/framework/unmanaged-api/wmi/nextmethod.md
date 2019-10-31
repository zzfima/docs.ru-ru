---
title: Функция Некстмесод (Справочник по неуправляемым API)
description: Функция Некстмесод извлекает следующий метод в перечислении.
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
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127363"
---
# <a name="nextmethod-function"></a>Функция Некстмесод
Извлекает следующий метод в перечислении, который начинается с вызова [бегинмесоденумератион](beginmethodenumeration.md).  

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
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`pName`  
заполняет Указатель, указывающий на `null` до вызова. Когда функция возвращает, адрес нового `BSTR`, который содержит имя метода. 

`ppSignatureIn`  
заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий параметры `in` для метода. 

`ppSignatureOut`  
заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий параметры `out` для метода. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Вызов функции [`BeginEnumeration`](beginenumeration.md) не выполнялся. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении больше нет свойств. |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

Вызывающий объект начинает последовательность перечисления, вызывая функцию [бегинмесоденумератион](beginmethodenumeration.md) , а затем вызывает функцию [некстмесод], пока функция не вернет `WBEM_S_NO_MORE_DATA`. При необходимости вызывающий объект завершает последовательность путем вызова [ендмесоденумератион](endmethodenumeration.md). Вызывающий объект может завершить перечисление раньше, вызвав [ендмесоденумератион](endmethodenumeration.md) в любое время.

## <a name="example"></a>Пример

C++ Пример см. в описании метода [Ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
