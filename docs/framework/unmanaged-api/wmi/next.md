---
title: Функция Next (Справочник по неуправляемым API)
description: Далее функция получает следующее свойство в перечисление.
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
ms.openlocfilehash: 240544330fa352cbfdc01944e4be6bcad28dc96f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373205"
---
# <a name="next-function"></a>Функция Next
Извлекает следующее свойство в перечисление, которое начинается с вызова [BeginEnumeration](beginenumeration.md).

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
[in] Этот параметр не используется.

`ptr`\
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`lFlags`\
[in] Зарезервировано. Этот параметр должен быть 0.

`pstrName`\
[out] Новый `BSTR` , содержащий имя свойства. Этот параметр можно задавать `null` Если имя не является обязательным.

`pVal`\
[out] Объект `VARIANT` подставлено значение свойства. Этот параметр можно задавать `null` Если значение не требуется. Если функция возвращает код ошибки `VARIANT` передается `pVal` слева без изменений.

`pvtType`\
[out] Указатель на `CIMTYPE` переменной ( `LONG` в который помещается тип свойства). Значение этого свойства может быть `VT_NULL_VARIANT`, в этом случае это необходимо определить фактический тип свойства. Этот параметр также может быть `null`.

`plFlavor`\
[out] `null`, или значение, которое получает данные на сервере-источнике свойства. См. в разделе [Примечание] возможные значения.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Возникла не вызывался метод [ `BeginEnumeration` ](beginenumeration.md) функции. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти, позволяющих начать новое перечисление. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Удаленный вызов процедур между текущего процесса и управления Windows не удалось. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Нет дополнительных свойств в перечислении. |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) метод.

Этот метод также возвращает системные свойства.

Если базовый тип свойства объекта пути, даты или времени или другой специальный тип, возвращаемый тип не содержит достаточно информации. Вызывающий объект должен проверить `CIMTYPE` для указанного свойства определить, является ли свойство ссылку на объект, даты или времени или другой специальный тип.

Если `plFlavor` не `null`, `LONG` значение получает сведения о происхождении свойства, следующим образом:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является свойством стандартной системы. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: Свойство наследуется от родительского класса. <br> Для экземпляра: Свойство, хотя наследуется от родительского класса, не был изменен в экземпляре.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: Свойство принадлежит к производному классу. <br> Для экземпляра: Свойство изменяется в экземпляре; то есть значение было предоставлено или квалификатор был добавлен или изменен. |

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** WMINet_Utils.idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)