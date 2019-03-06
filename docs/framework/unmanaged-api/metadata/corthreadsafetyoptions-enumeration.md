---
title: Перечисление CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360446"
---
# <a name="corthreadsafetyoptions-enumeration"></a>Перечисление CorThreadSafetyOptions

Задает флаги для выбора параметров безопасности потока.

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>Участники

|Член|Описание:|
|------------|-----------------|
|`MDThreadSafetyDefault`|Значение по умолчанию. Эквивалентно `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Указывает, что нельзя установить блокировку потоков чтения/записи.|
|`MDThreadSafetyOn`|Указывает, что блокировки потоков чтения/записи может быть задано.|

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorHdr.h

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
