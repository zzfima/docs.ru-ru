---
title: Метод IXCLRDataMethodDefinition::EnumInstance
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 420acda89858713f12ea87a8c8d3909682a3f5e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416727"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>Метод IXCLRDataMethodDefinition::EnumInstance

Перечисление экземпляров класса определения метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a>Параметры

`handle` [in, out] Дескриптор для перечисления экземпляров.

`instance` [out] Экземпляр перечисления.

## <a name="remarks"></a>Примечания

Указанный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует четвертый слот в таблице виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление CLRDataSourceType](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Интерфейс IXCLRDataMethodDefinition](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [Интерфейс IXCLRDataMethodInstance](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
