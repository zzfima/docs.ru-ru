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
ms.openlocfilehash: c324019e1e62701f4f2aaba1c00948b292ba6847
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127916"
---
# <a name="icordebugmodule2applychanges-method"></a>Метод ICorDebugModule2::ApplyChanges
Применяет изменения в метаданных и изменения в коде промежуточного языка MSIL к выполняющемуся процессу.  
  
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
 окне Размер (в байтах) разностных метаданных.  
  
 `pbMetadata`  
 окне Буфер, содержащий разностные метаданные. Адрес буфера возвращается методом [IMetaDataEmit2:: саведелтатомемори](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) .  
  
 Относительные виртуальные адреса (RVA) в метаданных должны относиться к началу кода MSIL.  
  
 `cbIL`  
 окне Размер (в байтах) разностного кода MSIL.  
  
 `pbIL`  
 окне Буфер, содержащий обновленный код MSIL.  
  
## <a name="remarks"></a>Заметки  
 Параметр `pbMetadata` находится в особом формате разностных метаданных (в виде выходных данных [IMetaDataEmit2:: саведелтатомемори](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` принимает предыдущие метаданные в качестве основы и описывает отдельные изменения, которые необходимо применить к этой базе.  
  
 В отличие от этого, параметр `pbIL[`] содержит новый код MSIL для обновленного метода и предназначен для полной замены предыдущего MSIL для этого метода.  
  
 Если разностный код MSIL и метаданные были созданы в памяти отладчика, отладчик вызывает `ApplyChanges` для отправки изменений в среду CLR. Среда выполнения обновляет свои таблицы метаданных, помещает новый код MSIL в процесс и настраивает JIT-компиляцию нового MSIL. После применения изменений отладчик должен вызвать [IMetaDataEmit2:: ресетенклог](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) , чтобы подготовиться к следующему сеансу редактирования. Затем отладчик может продолжить процесс.  
  
 Всякий раз, когда отладчик вызывает `ApplyChanges` для модуля, который имеет разностные метаданные, он также должен вызвать метод [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) с теми же разностными метаданными для всех своих копий метаданных этого модуля, за исключением копирования, используемой для отправки изменений. Если копия метаданных по каким-либо причинам не синхронизирована с фактическими метаданными, то отладчик всегда может создать копию и получить новую копию.  
  
 В случае сбоя метода `ApplyChanges` сеанс отладки находится в недопустимом состоянии и должен быть перезапущен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
