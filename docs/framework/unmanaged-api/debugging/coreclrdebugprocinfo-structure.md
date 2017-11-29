---
title: "Структура CoreClrDebugProcInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53616fb8e947d2a301dcfcb4e3870a9a9dc36ec1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugprocinfo-structure"></a>Структура CoreClrDebugProcInfo
Представляет процесс, который выполняется на удаленном компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`m_dwPID`|Идентификатор процесса, назначенный операционной системой.|  
|`m_dwInternalID`|Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере. Этот идентификатор перезапускается реже, чем идентификатор ОС.|  
|`m_wszName`|Командная строка процесса. Этот член может быть усечен.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Версии платформы .NET framework:** 3.5 SP1
