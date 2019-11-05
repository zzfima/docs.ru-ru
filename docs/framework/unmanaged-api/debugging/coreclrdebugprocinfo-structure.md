---
title: Структура CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: e12882e53d1aa2120ab5c4b6793d7f2e34be76eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132163"
---
# <a name="coreclrdebugprocinfo-structure"></a>Структура CoreClrDebugProcInfo
Представляет процесс, который выполняется на удаленном компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86. dll  
  
 **.NET Framework версии:** 3,5 SP1
