---
title: Функция Next (Справочник по неуправляемым интерфейсам API)
description: Следующая функция извлекает свойство Next в перечислении.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 587e085f6fe9f6c19d3605c673cd3bd6f68162f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127379"
---
# <a name="next-function"></a>Функция Next
Извлекает свойство Next в перечислении, которое начинается с вызова [BeginEnumeration](beginenumeration.md).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`\
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`pstrName`\
заполняет Новый `BSTR`, содержащий имя свойства. Можно задать для этого параметра значение `null`, если имя не является обязательным.

`pVal`\
заполняет `VARIANT` заполняется значением свойства. Этот параметр можно задать для `null`, если значение не является обязательным. Если функция возвращает код ошибки, `VARIANT`, переданный `pVal`, остается неизменной.

`pvtType`\
заполняет Указатель на переменную `CIMTYPE` (`LONG`, в которую помещается тип свойства). Значением этого свойства может быть `VT_NULL_VARIANT`. в этом случае необходимо определить фактический тип свойства. Этот параметр также можно `null`.

`plFlavor`\
[out] `null`или значение, получающее сведения об источнике свойства. Возможные значения см. в разделе [примечания].

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Вызов функции [`BeginEnumeration`](beginenumeration.md) не выполнялся. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Сбой удаленного вызова процедур между текущим процессом и управлением Windows. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении больше нет свойств. |

## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .

Этот метод также возвращает системные свойства.

Если базовым типом свойства является путь к объекту, дата или время или другой специальный тип, возвращаемый тип не содержит достаточной информации. Вызывающий объект должен проверить `CIMTYPE` для указанного свойства, чтобы определить, является ли свойство ссылкой на объект, датой или временем или другим специальным типом.

Если `plFlavor` не `null`, `LONG` значение получает сведения о происхождении свойства, как показано ниже.

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является стандартным системным свойством. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: свойство наследуется от родительского класса. <br> Для экземпляра: свойство, наследуемое от родительского класса, не было изменено экземпляром.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: свойство принадлежит производному классу. <br> Для экземпляра: свойство изменяется экземпляром; Это значит, что было предоставлено значение или был добавлен или изменен квалификатор. |

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
