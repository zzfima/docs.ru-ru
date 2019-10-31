---
title: Функция Жетобжекттекст (Справочник по неуправляемым API)
description: Функция Жетобжекттекст возвращает текстовую отрисовку объекта в синтаксисе MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 412e1ad503fa0e0b4f813298c0ac96ae80098c06
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102458"
---
# <a name="getobjecttext-function"></a>Функция GetObjectText
Возвращает текстовое представление объекта в синтаксисе MOF (MOF).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
окне Обычно 0. Если указано `WBEM_FLAG_NO_FLAVORS` (или 0x1), квалификаторы включаются без сведений о распространении или разновидности.

`pstrObjectText`   
заполняет Указатель на `null` записи. При возврате вновь выделенное `BSTR`, содержащее Синтаксис MOF для отображения объекта.  

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетобжекттекст](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .

Возвращенный текст MOF не содержит все сведения об объекте, но достаточно информации для компилятора MOF, чтобы иметь возможность воссоздать исходный объект. Например, не включаются распространенные квалификаторы или свойства родительского класса.

Для восстановления текста параметров метода используется следующий алгоритм:

1. Параметры переупорядочиваются в порядке их значений идентификаторов.
1. Параметры, указанные как `[in]` и `[out]`, объединяются в один параметр.
 
При вызове функции `pstrObjectText` должен быть указателем на `null`. Он не должен указывать на строку, допустимую до вызова метода, так как указатель не будет освобожден.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
