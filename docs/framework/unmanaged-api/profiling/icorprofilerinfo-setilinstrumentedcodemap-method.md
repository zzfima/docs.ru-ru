---
title: "Метод ICorProfilerInfo::SetILInstrumentedCodeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILInstrumentedCodeMap
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 35c87b98a8e0c02ab6f4bca7a4f7a16ff6839c6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>Метод ICorProfilerInfo::SetILInstrumentedCodeMap
Устанавливает карту кода для указанной функции с помощью указанных записей карты Microsoft промежуточного языка MSIL.  
  
> [!NOTE]
>  В .NET Framework версии 2.0, вызов `SetILInstrumentedCodeMap` на `FunctionID` что представляет универсальный функционировать в определенного домена приложения влияет на все экземпляры функции в домене приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которого требуется задать карту кода.  
  
 `fStartJit`  
 [in] Логическое значение, указывающее, является ли вызов `SetILInstrumentedCodeMap` метод является первым для какого-либо `FunctionID`. Задать `fStartJit` для `true` в первом вызове `SetILInstrumentedCodeMap` для данного `FunctionID`, а в `false` соответственно.  
  
 `cILMapEntries`  
 [in] Число элементов в `cILMapEntries` массива.  
  
 `rgILMapEntries`  
 [in] Массив структур COR_IL_MAP, каждый из которых определяет смещение MSIL.  
  
## <a name="remarks"></a>Примечания  
 Профилировщик часто вставляет операторы в исходном коде метода, позволяющие инструментировать этот метод (например, уведомлять о достижении заданной строки исходного). `SetILInstrumentedCodeMap`позволяет профилировщику сопоставление исходной инструкции MSIL в новые расположения. Можно использовать профилировщик [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) исходное смещение MSIL для заданного смещения собственного метода.  
  
 Отладчик будет предполагать, что каждое старое смещение ссылается на смещение в пределах исходного, неизмененного MSIL-код, и что каждое новое смещение ссылается на смещение MSIL в новом инструментированном коде. Карты должны быть отсортированы в порядке возрастания. Для правильной работы из пошаговой отладки, придерживайтесь следующих правил:  
  
-   Не меняйте порядок инструментированный код MSIL.  
  
-   Не удаляйте исходный код MSIL.  
  
-   Включить записи для всех точек следования из файла базы данных (PDB) программы на карте. Карты не выполнять интерполяцию, отсутствующие записи. Таким образом будет получено следующее сопоставление:  
  
     (0 старое, 0 новое)  
  
     (5 старого, 10 новых)  
  
     (9 старого, 20 новой)  
  
    -   Старое смещение 0, 1, 2, 3 или 4 будет сопоставлено новому смещению 0.  
  
    -   Старое смещение 5, 6, 7 или 8 будет сопоставлено новому смещению 10.  
  
    -   Старое смещение 9 или более поздней версии будут сопоставлены новому смещению 20.  
  
    -   Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлено старому смещению 0.  
  
    -   Новый смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлено старому смещению 5.  
  
    -   Новое смещение 20 или выше будет сопоставлено старому смещению 9.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
