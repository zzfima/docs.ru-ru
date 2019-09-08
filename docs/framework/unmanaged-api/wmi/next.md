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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95cea4cb3e7e7df2b6b52256a440b9a8d544f2db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798409"
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
заполняет Новый `BSTR` объект, содержащий имя свойства. Этот параметр можно установить в `null` значение, если имя не является обязательным.

`pVal`\
заполняет `VARIANT` Заполняется значением свойства. Этот параметр можно задать равным `null` , если значение не является обязательным. Если функция возвращает код ошибки, `VARIANT` `pVal` переданный метод остается неизменным.

`pvtType`\
заполняет Указатель на `CIMTYPE` переменную `LONG` (в которой размещается тип свойства). Значением этого свойства может быть `VT_NULL_VARIANT`, в этом случае необходимо определить фактический тип свойства. Этот параметр также может иметь `null`следующий аргумент:.

`plFlavor`\
заполняет `null`или значение, получающее сведения об источнике свойства. Возможные значения см. в разделе [примечания].

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Нет вызова [`BeginEnumeration`](beginenumeration.md) функции. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Сбой удаленного вызова процедур между текущим процессом и управлением Windows. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении больше нет свойств. |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .

Этот метод также возвращает системные свойства.

Если базовым типом свойства является путь к объекту, дата или время или другой специальный тип, возвращаемый тип не содержит достаточной информации. Вызывающий объект должен проверить `CIMTYPE` для указанного свойства, чтобы определить, является ли свойство ссылкой на объект, датой или временем или другим специальным типом.

Если `plFlavor` параметр не `null`равен, `LONG` значение получает сведения о происхождении свойства, как показано ниже.

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является стандартным системным свойством. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: Свойство наследуется от родительского класса. <br> Для экземпляра: Свойство, наследуемое от родительского класса, не было изменено экземпляром.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: Свойство принадлежит производному классу. <br> Для экземпляра: Свойство изменяется экземпляром; Это значит, что было предоставлено значение или был добавлен или изменен квалификатор. |

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
