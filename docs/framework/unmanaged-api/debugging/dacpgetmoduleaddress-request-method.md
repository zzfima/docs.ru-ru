---
title: DacpGetModuleАдрес::Запрос Метод
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179198"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleАдрес::Запрос Метод

Выполняет запрос на заселяют структуру из заданной структуры времени выполнения.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Параметры

`pDataModule`\
(в) Указатель на модуль данных семян.

## <a name="remarks"></a>Remarks

Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек. Проще всего имитировать реализацию:

- Возврат значения, полученного `Request` от вызова `IXCLRDataModule*` метода по параметру со следующими параметрами:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** Нет **библиотеки:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Отладки](index.md)
- [Интерфейс DacpGetModuleАдрес](dacpgetmoduleaddress-structure.md)
