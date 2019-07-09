---
title: Метод ICorProfilerInfo::SetILInstrumentedCodeMap
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e41df91ceb9e4b776c2aa1ce864b7e09ec485fd5
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661955"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>Метод ICorProfilerInfo::SetILInstrumentedCodeMap

Задает карту кода для заданной функции, используя указанные записи карты Microsoft промежуточного языка MSIL.

> [!NOTE]
> В .NET Framework версии 2.0, вызвав `SetILInstrumentedCodeMap` на `FunctionID` что представляет универсальный работать в конкретный домен приложения будет влиять на все экземпляры этой функции в домене приложения.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a>Параметры

`functionId`\
[in] Идентификатор функции, для которого требуется задать карты кода.

`fStartJit`\
[in] Логическое значение, указывающее ли вызов `SetILInstrumentedCodeMap` метод является первым для какого-либо `FunctionID`. Задайте `fStartJit` для `true` в первом вызове `SetILInstrumentedCodeMap` для заданного `FunctionID`, а в `false` соответственно.

`cILMapEntries`\
[in] Число элементов в `cILMapEntries` массива.

`rgILMapEntries`\
[in] Массив структур COR_IL_MAP, каждый из которых задает смещение MSIL.

## <a name="remarks"></a>Примечания

Профилировщик часто вставляет операторы в исходный код метода, позволяющие инструментировать этот метод (например, для уведомления при достижении заданной строки исходного). `SetILInstrumentedCodeMap` позволяет профилировщику для сопоставления исходного инструкций MSIL в новые расположения. Можно использовать профилировщик [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) метод, чтобы получить исходное смещение MSIL для заданного смещения машинного кода.

Отладчик предположит, что каждое старое смещение ссылается на смещение в исходном, неизмененном MSIL-код, и что каждое новое смещение ссылается на смещение MSIL в новом коде инструментированной. Карты должны быть отсортированы в порядке возрастания. Для начала работы должным образом, придерживайтесь следующих рекомендаций.

- Не переупорядочивают инструментированный код MSIL.

- Не удаляйте исходный код MSIL.

- Включите записи для всех точек следования из файла базы данных (PDB) программы на карте. Карты не интерполирует недостающие записи. Таким образом Если на следующей карте:

  (0 старое, 0 новое)

  (5 старше 10 новых)

  (9 старый, 20 новых)

  - Старое смещение 0, 1, 2, 3 или 4 будет сопоставляться новое смещение 0.

  - Старое смещение 5, 6, 7 или 8 будет сопоставляться новое смещение 10.

  - Старое смещение 9 или более поздней версии будет сопоставляться новое смещение 20.

  - Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлен старое смещение 0.

  - Новое смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлен старое смещение 5.

  - Новое смещение 20 или более поздней версии будет сопоставлен старое смещение 9.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
