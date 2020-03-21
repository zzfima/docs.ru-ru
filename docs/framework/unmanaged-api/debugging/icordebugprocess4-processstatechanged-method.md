---
title: ICorDebugПроцесс4::ProcessStateChanged Метод
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178632"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugПроцесс4::ProcessStateChanged Метод

Уведомляет конвейер ICorDebug о том, что недогибающий процесс продолжает выполнение debugee.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Параметры

 `eChange`\
(в) Участник [перечисления CorDebugStateChange,](cordebugstatechange-enumeration.md) описывающий состояние выполнения процесса.

## <a name="remarks"></a>Remarks

Предоставленный метод является `ICorDebugProcess4` частью интерфейса и соответствует четвертому слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок:** Ни один

 **Библиотека:** Ни один

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладки](index.md)
