---
title: IXCLRDataProcess::EnumMethodInstanceByAddress Метод
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176660"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>IXCLRDataProcess::EnumMethodInstanceByAddress Метод

Перечисляет экземпляры метода этого процесса, начиная с смещения адреса.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>Параметры

`handle`\
(в) Ручка для перечисления экземпляров метода.

`mod`\
(ваут) Перечисленный экземпляр метода.

## <a name="remarks"></a>Remarks

Предоставляемый метод является `IXCLRDataProcess` частью интерфейса и соответствует 28-му слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).
**Заголовок:** Нет **библиотеки:** Нет **.NET Рамочные версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также раздел

- [Перечисление CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Отладки](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
