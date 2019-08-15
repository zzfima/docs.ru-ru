---
title: Функция Get (Справочник по неуправляемым API)
description: Функция Get извлекает указанное значение свойства.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 265d3edbd3175eebcf6fd35be24f5b66144c960f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037956"
---
# <a name="get-function"></a>Функция Get

Возвращает указанное значение свойства, если оно существует.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
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

`wszName`\
окне Имя свойства.

`lFlags`\
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`pVal`\
заполняет Если функция возвращается успешно, содержит значение `wszName` свойства. `pval` Аргументу присваивается правильный тип и значение для квалификатора.

`pvtType`\
заполняет Если функция возвращает значение успешно, содержит [константу типа CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) , которая указывает тип свойства. Его значение также может быть `null`. 

`plFlavor`\
заполняет Если функция возвращается успешно, получает сведения об источнике свойства. Его значением может быть `null`или одна из следующих констант WBEM_FLAVOR_TYPE, определенных в файле заголовка *вбемкли. h* : 

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является стандартным системным свойством. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: Свойство наследуется от родительского класса. <br> Для экземпляра: Свойство, наследуемое от родительского класса, не было изменено экземпляром.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: Свойство принадлежит производному классу. <br> Для экземпляра: Свойство изменяется экземпляром; Это значит, что было предоставлено значение или был добавлен или изменен квалификатор. |

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не найдено. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .

`Get` Функция также может возвращать системные свойства.

Аргументу присваивается правильный тип и значение для квалификатора и com-функции [вариантинит](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) `pVal`

## <a name="requirements"></a>Требования

 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** WMINet_Utils. idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
