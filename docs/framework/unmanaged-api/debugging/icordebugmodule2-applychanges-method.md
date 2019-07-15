---
title: Метод ICorDebugModule2::ApplyChanges
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 860b87b09ee487f893a1bba2aaa34292c50ffcb7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764336"
---
# <a name="icordebugmodule2applychanges-method"></a>Метод ICorDebugModule2::ApplyChanges
Применяет изменения в метаданных и изменения в код на промежуточном языке (MSIL) к выполняющемуся процессу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbMetadata`  
 [in] Размер в байтах, изменений метаданных.  
  
 `pbMetadata`  
 [in] Буфер, содержащий метаданные изменений. Адрес буфера возвращается из [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) метод.  
  
 Относительные виртуальные адреса (RVA) в метаданных должен указываться относительно начала кода на языке MSIL.  
  
 `cbIL`  
 [in] Размер в байтах, разностных кода MSIL.  
  
 `pbIL`  
 [in] Буфер, содержащий обновленный код MSIL.  
  
## <a name="remarks"></a>Примечания  
 `pbMetadata` Параметр имеет формат метаданных специальных изменений (как выходные, [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` принимает предыдущий метаданные базовым и описание отдельных изменений для применения к базе.  
  
 Напротив, `pbIL[`] параметр содержит новый код MSIL для метода обновленные и предназначен для полной замены предыдущих MSIL для этого метода  
  
 При создании разностного кода MSIL и метаданных в памяти в отладчике вызывает `ApplyChanges` для отправки изменений в общеязыковой среде выполнения (CLR). Среда выполнения обновляет свою таблицу метаданных, помещает новый код MSIL в процесс и настраивает just-in-time (JIT) компиляции нового кода MSIL. Если изменения были применены, отладчик должен вызвать [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) для подготовки для следующего сеанса редактирования. Затем он может продолжить процесс.  
  
 Каждый раз, когда он вызывает `ApplyChanges` модуля, который содержит метаданные изменений, он должен также вызывать [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) с одинаковыми метаданными изменений на всех копий этого модуля метаданных, за исключением копирования используется для выдачи изменений. Если копия метаданных каким-либо образом становится out синхронизированной с фактическими метаданными, отладчик всегда может выбрасывать эту копию и получить новую.  
  
 Если `ApplyChanges` метод завершается ошибкой, отладочные сеанс находится в недопустимом состоянии и должен быть перезапущен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
