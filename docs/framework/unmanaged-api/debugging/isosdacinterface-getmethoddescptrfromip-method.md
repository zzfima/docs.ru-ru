---
title: Метод ISOSDacInterface::GetMethodDescPtrFromIP
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: cd256250021436e611142de11c3625a21aeec814
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764740"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>Метод ISOSDacInterface::GetMethodDescPtrFromIP

Извлекает указатель MethodDesc, соответствующий метод, содержащий адрес заданной инструкции машинного кода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a>Параметры

`ip`\
[in] Адрес в пределах метода во время выполнения.

`ppMD`\
[out] Адрес `MethodDesc` для конкретного метода.

## <a name="remarks"></a>Примечания

Указанный метод является частью [ `ISOSDacInterface` интерфейс](isosdacinterface-interface.md) и соответствует 21 слот в таблице виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)
