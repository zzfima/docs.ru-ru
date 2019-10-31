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
ms.openlocfilehash: 5f618f6779f6931785bba18f70fb1ac9baf46753
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137194"
---
# <a name="icordebugprocess2getversion-method"></a>Метод ICorDebugProcess2::GetVersion

Возвращает номер версии среды CLR, которая выполняется в этом процессе.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a>Параметры

`version`\
заполняет Указатель на структуру COR_VERSION, в которой хранится номер версии среды выполнения.

## <a name="remarks"></a>Заметки

Метод `GetVersion` возвращает код ошибки, если в процессе не была загружена среда выполнения.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
