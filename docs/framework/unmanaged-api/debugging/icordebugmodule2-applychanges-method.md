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
ms.openlocfilehash: 5a406e945a67352bc7f126b40bd56f4a11dd693b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419547"
---
# <a name="icordebugmodule2applychanges-method"></a>Метод ICorDebugModule2::ApplyChanges
Применяет изменения в метаданных и изменений в код на промежуточном языке (MSIL) к работающему процессу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cbMetadata`  
 [in] Размер в байтах, дельта метаданных.  
  
 `pbMetadata`  
 [in] Буфер, содержащий метаданные изменений. Адрес буфера возвращается из [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) метод.  
  
 Относительные виртуальные адреса (RVA) в метаданных должен указываться относительно начала кода на языке MSIL.  
  
 `cbIL`  
 [in] Размер в байтах разности код MSIL.  
  
 `pbIL`  
 [in] Буфер, содержащий обновленный код MSIL.  
  
## <a name="remarks"></a>Примечания  
 `pbMetadata` Параметр имеет формат метаданных специальные дельта (как выходные, [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` берет предыдущие метаданные в качестве базового и описывает отдельные изменения, применяемые к этой базе.  
  
 Напротив, `pbIL[`] параметр содержит новый код MSIL для обновленного метода и предназначен для полной замены предыдущих MSIL для этого метода  
  
 При создании разностного кода MSIL и метаданных в памяти отладчика, он вызывает `ApplyChanges` для отправки изменений в общеязыковой среде выполнения (CLR). Среда выполнения обновляет свою таблицу метаданных, помещает новый код MSIL в процесс и настраивает в момент компиляции нового кода MSIL. Если изменения были применены, отладчик должен вызвать [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) для подготовки для следующего сеанса редактирования. Затем он может продолжить процесс.  
  
 Каждый раз, когда он вызывает `ApplyChanges` модуля, который содержит метаданные изменений, он также должен вызвать [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) с одинаковыми метаданными изменений на все его копии метаданных этого модуля, за исключением копирования используется для выдачи изменений. Если копии метаданных рассинхронизации ожидания для синхронизации с фактическими метаданными, отладчик всегда может отбросить эту копию и получить новую.  
  
 Если `ApplyChanges` сбой метода отладки сеанс находится в недопустимом состоянии и должен быть перезапущен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
