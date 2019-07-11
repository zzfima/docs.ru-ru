---
title: Перечисление AssemblyFlags
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 502e7841f8c413aa48732bcea0b6c2178d70c061
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776446"
---
# <a name="assemblyflags-enumeration"></a>Перечисление AssemblyFlags
Содержит значения, описывающие возможности времени выполнения сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Указывает, что экспортированный тип определения являются неявными внутри файлов, составляющих сборку. В .NET Framework версий 1.0 и 1.1 это значение всегда считается задать.|  
|`afImplicitResources`|Указывает, что определения ресурсов являются неявными внутри файлов, составляющих сборку. В .NET Framework 1.0 и 1.1 это значение всегда считается задать.|  
|`afNonSideBySideAppDomain`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном домене приложения.|  
|`afNonSideBySideProcess`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном процессе.|  
|`afNonSideBySideMachine`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются на одном компьютере.|  
  
## <a name="remarks"></a>Примечания  
 Значения между 0x0010 и 0x0070, включительно, используются для описания функции обеспечения совместимости side-by-side по ссылке сборки. Если ни одно из этих значений, предполагается, что сборки side-by-side-совместимыми.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MsCorEE.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
