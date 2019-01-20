---
title: Метод IXCLRDataProcess::EndEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a48a7fc9a141354666c50b1f6da8f1aaa180ff6c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416624"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a>Метод IXCLRDataProcess::EndEnumMethodInstancesByAddress

Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a>Параметры

`handle` [out] Дескриптор для перечисления экземпляров метода.

## <a name="remarks"></a>Примечания

Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 29 слот в таблице виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление CLRDataSourceType](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Интерфейс IXCLRDataProcess](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
