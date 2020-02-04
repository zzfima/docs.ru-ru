---
title: Перечисление CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: 99fc89d1aee6c9f0fbffc193e12ce563e820f268
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789287"
---
# <a name="cordebugrecordformat-enumeration"></a>Перечисление CorDebugRecordFormat
Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|Данные представляют собой 32-разрядную запись Windows-исключения.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|Данные представляют собой 64-разрядную запись Windows-исключения.|  
  
## <a name="remarks"></a>Заметки  
 Член перечисления `CorDebugRecordFormat` передается методу [DecodeEvent](icordebugprocess6-decodeevent-method.md) для указания формата массива байтов в его `pRecord` аргументе.  
  
> [!NOTE]
> Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления отладки](debugging-enumerations.md)
