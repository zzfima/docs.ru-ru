---
title: Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a67f93a3f3f75b89bc3f0240995471bc0bf44992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419761"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Настраивает порядок, согласно которому отладчик обрабатывает обновления находящихся в памяти метаданных в целевом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 Объект [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) значение перечисления, указывающее, отображаются ли обновления в памяти метаданных в целевом процессе (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) или невидимое (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) для отладчика.  
  
## <a name="remarks"></a>Примечания  
 Обновления для метаданных в целевом процессе могут поступать из режима "Изменить и продолжить", профилировщика или <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess7](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
