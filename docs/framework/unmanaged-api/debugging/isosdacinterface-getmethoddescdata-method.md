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
ms.openlocfilehash: cdbf662c664d6c87b2fa17bcb10d735b0f573dd2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632317"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Метод ISOSDacInterface::GetMethodDescData

Получает данные для заданный указатель MethodDesc.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a>Параметры

`methodDesc`\
[in] Адрес MethodDesc.

`ip`\
[in] IP-адрес метода.

`data`\
[out] Данные, связанные с MethodDesc, возвращенный внутренним API.

`cRevertedRejitVersions`\
[out] Число версий rejit возвращенного в предыдущее состояние.

`rgRevertedRejitData`\
[out] Данные, связанные с версиями возвращенного в предыдущее состояние rejit, возвращенный внутренним API.

`pcNeededRevertedRejitData`\
[out] Число байтов, необходимое для хранения данных, связанные с восстанавливаемой версиями ReJit.

## <a name="remarks"></a>Примечания

Указанный метод является частью `ISOSDacInterface` интерфейса и соответствует 20 слот в таблице виртуального метода. Чтобы иметь возможность использовать их, [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) должен быть определен как 64-разрядное целое число без знака.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)
