---
title: "Перечисление AssemblyFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91760b6d16b663257bf3d89915da3bd88b3411bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyflags-enumeration"></a>Перечисление AssemblyFlags
Содержит значения, описывающие функции времени выполнения сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Указывает, что определения экспортируемого типа неявные внутри файлов, которые составляют сборку. В .NET Framework версий 1.0 и 1.1 это значение всегда является предполагается заданы.|  
|`afImplicitResources`|Указывает, что определения ресурсов неявное внутри файлов, которые составляют сборку. В .NET Framework 1.0 и 1.1 это значение всегда предполагается требуется задать.|  
|`afNonSideBySideAppDomain`|Указывает, что сборка не может выполняться с другими своими версиями, если они выполняются в том же домене приложения.|  
|`afNonSideBySideProcess`|Указывает, что сборка не может выполняться с другими своими версиями, если они выполняются в одном процессе.|  
|`afNonSideBySideMachine`|Указывает, что сборка не может выполняться с другими своими версиями, если они выполняются на том же компьютере.|  
  
## <a name="remarks"></a>Примечания  
 Значения между 0x0010 и 0x0070, включительно, используются для описания функций обеспечения совместимости side-by-side по ссылке сборки. Если ни одно из этих значений задаются сборки предполагается side-by-side-совместимыми.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MsCorEE.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
