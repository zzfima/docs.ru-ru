---
title: Метод ICorDebugProcess4::ProcessStateChanged
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
ms.openlocfilehash: 5e3a6714489e2051a09b5855ab9f911ef2f57450
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632287"
---
# <a name="icordebugprocess4processstatechanged-method"></a>Метод ICorDebugProcess4::ProcessStateChanged

Уведомляет конвейера ICorDebug о том, что внепроцессные отладчик процесс продолжает выполнение отлаживаемого кода.

## <a name="syntax"></a>Синтаксис

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Параметры

 `eChange`\
[in] Является членом [перечисление CorDebugStateChange](cordebugstatechange-enumeration.md) описывающие изменения в состоянии выполнения процесса.

## <a name="remarks"></a>Примечания

Указанный метод является частью `ICorDebugProcess4` интерфейса и соответствует четвертый слот в таблице виртуального метода.

## <a name="requirements"></a>Требования

 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** Нет

 **Библиотека:** Нет
 
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
