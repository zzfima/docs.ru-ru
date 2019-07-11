---
title: Метод IXCLRDataMethodInstance::GetRepresentativeEntryAddress
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 5c79e916a06e796fc87b57eb949cccda77b8a9bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744662"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>Метод IXCLRDataMethodInstance::GetRepresentativeEntryAddress

Получает наиболее характерные адрес точки входа для компиляция в собственном коде все возможные точки входа для метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Параметры

`addr`\
[out] Адрес типичному машинную точку входа для метода.

## <a name="remarks"></a>Примечания

Указанный метод является частью [ `IXCLRDataMethodInstance` интерфейс](ixclrdatamethodinstance-interface.md) и соответствует 19 слот в таблице виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
