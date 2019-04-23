---
title: Перечисление WriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e4328b75a7f6fecc28cd620ec3ac18460316c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111141"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>Перечисление WriteableMetadataUpdateMode
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Предоставляет значения, указывающие, будут ли видны в отладчике обновления копии метаданных в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Участники  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Поддерживает совместимость с предыдущими версиями платформы .NET Framework, делая видимыми обновления находящихся в памяти метаданных. Дополнительные сведения см. в разделе "Примечания".|  
|`AlwaysShowUpdates`|Делает обновления находящихся в памяти метаданных видимыми в отладчике.|  
  
## <a name="remarks"></a>Примечания  
 Является членом `WriteableMetadataUpdateMode` перечисления может быть передан [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) метод для управления, обновляются ли в памяти метаданных в целевом процессе являются видимыми для отладчика.  
  
 Параметр `LegacyCompatPolicy` обеспечивает такое же поведение, как и до версии 4.5.2 платформы .NET Framework. Чаще всего это означает, что метаданные из обновлений не видны. В то же время вызовы ряда методов отладчика неявно вынуждают его делать обновления видимыми. Например, если отладчик передает [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) индекс переменной, не найден в исходных метаданных метода, все метаданные для модуля обновляется до моментального снимка, текущее состояние соответствия процесс. Другими словами, при наличии параметра `LegacyCompatPolicy` отладчик может не видеть вообще, видеть частично или видеть все доступные обновления метаданных в зависимости от того, как он использует другие части неуправляемого API отладки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Метод SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
