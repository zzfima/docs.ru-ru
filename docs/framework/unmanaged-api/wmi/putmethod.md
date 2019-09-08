---
title: Функция Путмесод (Справочник по неуправляемым API)
description: Функция Путмесод создает метод.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2b41cbbade9da5c2095309b9039b8ce2758f6f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798366"
---
# <a name="putmethod-function"></a>Функция Путмесод
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
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`  
окне Имя создаваемого метода. 

`lFlags`  
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`pSignatureIn`  
окне Указатель на копию [системного класса __Parameters](/windows/desktop/WmiSdk/--parameters) , которая содержит `in` параметры для метода. Этот параметр игнорируется, если имеет `null`значение.  

`pSignatureOut`  
окне  Указатель на копию [системного класса __Parameters](/windows/desktop/WmiSdk/--parameters) , которая содержит `out` параметры для метода. Этот параметр игнорируется, если имеет `null`значение.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Параметр метода, указанный в объектах *пинсигнатуре* и паутсигнатуре, имеет разные квалификаторы. `[in, out]`
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | В параметре метода отсутствует спецификация квалификатора **идентификатора** . |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Серия ИДЕНТИФИКАТОРов, назначенных параметрам метода, не является последовательным или не начинается с 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Возвращаемое значение метода имеет квалификатор **идентификатора** . |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Предпринята попытка повторно использовать существующее имя метода из родительского класса, и подписи не совпали. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова метода [ивбемклассобжект::P утмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

Этот вызов метода поддерживается, только если `ptr` является определением класса CIM. Управление методами недоступно из [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры CIM.

Пользователи не могут создавать методы с именами, которые начинаются или заканчиваются символом подчеркивания. Он зарезервирован для системных классов и свойств.

Для метода `in` параметры и `out` описаны как свойства в объектах [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

Параметр можно определить, добавив одно и то же свойство в оба объекта, на `pInSignature` которые указывают `pOutSignature` параметры и. `[in/out]` В этом случае свойства имеют одинаковое значение квалификатора **идентификатора** .

Каждое свойство в объекте класса [__Parameters](/windows/desktop/WmiSdk/--parameters) , отличном `ReturnValue` от, должно иметь квалификатор **ID** , числовое значение, начинающееся с нуля, определяющее порядок, в котором отображаются параметры. Ни один из двух параметров не может иметь одинаковое значение **идентификатора** , и значение **идентификатора** не может быть пропущено. При возникновении `PutMethod` любого из этих условий функция `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`возвращает значение.

## <a name="example"></a>Пример

Пример см. в описании метода [ивбемклассобжект::P утмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
