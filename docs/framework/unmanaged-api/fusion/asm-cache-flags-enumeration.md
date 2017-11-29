---
title: "Перечисление ASM_CACHE_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASM_CACHE_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: ASM_CACHE_FLAGS
helpviewer_keywords: ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 767cae15c37b8c62d47085533ea9fa3ce4957963
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="asmcacheflags-enumeration"></a>Перечисление ASM_CACHE_FLAGS
Указывает источник сборки, представленного [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Выполняет перечисление кэша сборок, предварительно скомпилированных с помощью Ngen.exe.|  
|`ASM_CACHE_GAC`|Перечисляет в глобальном кэше сборок.|  
|`ASM_CACHE_DOWNLOAD`|Перечисляет сборки, которые были загружены по требованию или были теневого копирования.|  
|`ASM_CACHE_ROOT`|Указывает, что [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) функция должна возвращать путь в глобальный кэш сборок для общеязыковой среды выполнения (CLR) версии 2.0. Имеет смысл только в контексте вызова [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Указывает, что [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) функция должна возвращать путь в глобальный кэш сборок для среды CLR версии 4. Имеет смысл только в контексте вызова [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [IAssemblyCacheItem-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
