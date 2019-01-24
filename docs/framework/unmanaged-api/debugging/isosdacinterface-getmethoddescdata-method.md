---
title: Метод ISOSDacInterface::GetMethodDescData
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e56f837c4d3362ec6e71030e4fb475df42b9fba4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639964"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Метод ISOSDacInterface::GetMethodDescData

Получает данные для заданного [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    void                       *data,
    ULONG                      cRevertedRejitVersions,
    void                      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a>Параметры

`methodDesc` [in] Адрес MethodDesc.

`ip` [in] IP-адрес метода.

`data` [out] Данные, связанные с MethodDesc, возвращенный внутренним API. Структура необходимо по крайней мере 168 байта.

`cRevertedRejitVersions` [out] Число версий rejit возвращенного в предыдущее состояние.

`rgRevertedRejitData` [out] Данные, связанные с версиями возвращенного в предыдущее состояние rejit, возвращенный внутренним API. Структура необходимо по крайней мере 24 байта.

`pcNeededRevertedRejitData` [out] Число байтов, необходимое для хранения данных, связанные с восстанавливаемой версиями ReJit.

## <a name="remarks"></a>Примечания

Указанный метод является частью `ISOSDacInterface` интерфейса и соответствует 20 слот в таблице виртуального метода. Также `CLRDATA_ADDRESS` являются 64-разрядного целого числа без знака.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Интерфейс ISOSDacInterface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
