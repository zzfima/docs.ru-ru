---
title: Функция метода WebMethod (Справочник по неуправляемым интерфейсам API)
description: Функция метода WebMethod получает сведения о методе.
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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102587"
---
# <a name="getmethod-function"></a>Функция GetMethod

Получает сведения об указанном методе.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
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

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
окне Имя метода. Этот параметр не может быть `null` и должен указывать на допустимый `LPCWSTR`.

`lFlags`\
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`ppInSignature`\
заполняет Указатель на адрес экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , который описывает входные параметры метода. Этот параметр пропускается, если он имеет значение `null`.

`ppOutSignature`\
заполняет Указатель на адрес экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , который описывает выходные параметры метода. Этот параметр пропускается, если он имеет значение `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не найдено. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект::-Method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .

Система управления Windows может установить указатель [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) на `null`, если метод не имеет параметров.

В `ppInSignature` и `ppOutSignature` описать параметры in и out соответственно как свойства в экземпляре `IWbemClassObject` класса System [_Parameters](/windows/desktop/WmiSdk/--parameters). Свойства в `ppInSignature` именуются `Param`*n*, где *n* — это расположение параметра в сигнатуре метода (например, `Param1`, `Param2`и т. д.). Свойства в `ppOutSignature` также называются `Param`*n*, а возвращаемое значение называется `ReturnValue`. Дополнительные сведения и пример см. в разделе [метод ивбемклассобжект::](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)Method.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
