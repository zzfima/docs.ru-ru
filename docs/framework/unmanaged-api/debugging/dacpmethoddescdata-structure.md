---
title: Структура DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 567dc3942f79b6bfd29338b9103083aa64e66451
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203201"
---
# <a name="dacpmethoddescdata-structure"></a>Структура DacpMethodDescData

Определяет транспорт буфер сведения среды выполнения метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a>Участники

| Член                       | Описание                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Указывает, имеет ли среда выполнения машинного кода, доступных для данного экземпляра метода. |
| `bIsDynamic`                 | Указывает, если метод создается динамически во время создания облегченного кода.           |
| `wSlotNumber`                | Метод номер ячейки в таблицу методов.                                                   |
| `NativeCodeAddr`             | Начального адреса собственного метода.                                                            |
| `data`                       | Указатель на буфер, внутреннего использования средой выполнения.                                             |
| `MethodDescPtr`              | Указатель на `MethodDesc` в среде выполнения.                                                     |
| `nativeCodeInfo`             | Указатель на буфер, используется внутренним образом средой выполнения для отслеживания методов.                            |
| `moduleInfo`                 | Указатель на буфер для внутреннего применения средой выполнения сведений о модуле.                      |
| `MDToken`                    | Токен, связанный с данный метод.                                                         |
| `payloadGC`                  | Указатель на буфер сбора мусора внутреннего использования средой выполнения.                          |
| `payloadGC2`                 | Указатель на буфер сбора мусора внутреннего использования средой выполнения.                          |
| `managedDynamicMethodObject` | Если метод является динамическим, среда выполнения использует этот буфер внутренне, для отслеживания данных.     |
| `requestedIP`                | Используется для заполнения структуры на каждый запрос при указанного адреса машинного кода.                    |
| `rejitDataCurrent`           | Сведения о последней инструментированной версии метода.                                   |
| `rejitDataRequested`         | Rejit сведения для запрошенного собственного адреса.                                             |
| `cJittedRejitVersions`       | Количество раз, когда метод был rejitted через инструментарий.                           |

## <a name="remarks"></a>Примечания

Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек. Чтобы использовать его, определите структуру, как указано выше.

## <a name="requirements"></a>Требования
**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Общие типы данных](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
