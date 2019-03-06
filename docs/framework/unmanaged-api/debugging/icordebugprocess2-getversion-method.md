---
title: Метод ICorDebugProcess2::GetVersion
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f3be81431201a4bb6011ea9b8f973061d3d101
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361243"
---
# <a name="icordebugprocess2getversion-method"></a>Метод ICorDebugProcess2::GetVersion

Возвращает номер версии среда CLR (CLR), на котором выполняется в этом процессе.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a>Параметры

`version`\
[out] Указатель на структуру COR_VERSION, которая хранит номер версии среды выполнения.

## <a name="remarks"></a>Примечания

`GetVersion` Метод возвращает код ошибки, если среда выполнения не была загружена в процесс.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
