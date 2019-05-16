---
title: Получить функцию (Справочник по неуправляемым API)
description: Функция Get получает значение указанного свойства.
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
ms.openlocfilehash: b8a1942f903b1c7c15e58077e35b6a72a86a9419
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636530"
---
# <a name="get-function"></a>Функция Get

Получает значение указанного свойства, если он существует.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```
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
[in] Этот параметр не используется.

`ptr`\
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszName`\
[in] Имя свойства.

`lFlags`\
[in] Зарезервировано. Этот параметр должен быть 0.

`pVal`\
[out] Если функция возвращает успешно, содержит значение `wszName` свойства. `pval` Аргумент назначается правильный тип и значение квалификатора.

`pvtType`\
[out] Если функция возвращает успешно, содержит [тип CIM константа](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) , указывающее тип свойства. Его значение может также быть `null`. 

`plFlavor`\
[out] Если функция возвращает успешно, получает сведения о происхождении свойства. Его значение может быть `null`, или один из следующих WBEM_FLAVOR_TYPE констант, определенных в *WbemCli.h* заголовочный файл: 

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является свойством стандартной системы. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: Свойство наследуется от родительского класса. <br> Для экземпляра: Свойство, хотя наследуется от родительского класса, не был изменен в экземпляре.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: Свойство принадлежит к производному классу. <br> Для экземпляра: Свойство изменяется в экземпляре; то есть значение было предоставлено или квалификатор был добавлен или изменен. |

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не найден. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) метод.

`Get` Функция также может возвращать свойства системы.

`pVal` Аргумент назначается правильный тип и значение для квалификатора и COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) функции

## <a name="requirements"></a>Требования

 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** WMINet_Utils.idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
