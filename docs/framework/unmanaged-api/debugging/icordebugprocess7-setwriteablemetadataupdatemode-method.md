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
ms.openlocfilehash: 35767529d9433764b7eed0b3b4acdd806f399962
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792183"
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
  
## <a name="parameters"></a>Параметры  
 `flags`  
 Значение перечисления [вритеаблеметадатаупдатемоде](writeablemetadataupdatemode-enumeration.md) , указывающее, являются ли обновления в памяти в целевом процессе видимыми (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) или невидимыми (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) отладчиком.  
  
## <a name="remarks"></a>Заметки  
 Обновления для метаданных в целевом процессе могут поступать из режима "Изменить и продолжить", профилировщика или <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess7](icordebugprocess7-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
