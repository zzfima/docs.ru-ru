---
title: "Метод ICorRuntimeHost::MapFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd156aac23cdca446bcf2666ce36e91fef6d5392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostmapfile-method"></a>Метод ICorRuntimeHost::MapFile
Сопоставляет указанный файл в память. Этот метод устарел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hFile`  
 [in] Дескриптор файла для сопоставления.  
  
 `hMapAddress`  
 [out] Начальный адрес памяти, с которого начинается файл сопоставления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версия платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также  
 [ICorRuntimeHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
