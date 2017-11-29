---
title: "Метод ICorDebugThread2::GetConnectionID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetConnectionID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae852fe91bdb15007437ea6f2c61cbaa49a6918b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2getconnectionid-method"></a>Метод ICorDebugThread2::GetConnectionID
Получает идентификатор подключения для этого объекта ICorDebugThread2.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pdwConnectionId`  
 [out] Объект `CONNID` , представляющий идентификатор соединения.  
  
## <a name="remarks"></a>Примечания  
 `GetConnectionID` Метод возвращает нуль в `pdwConnectionId` параметра, если этот поток не является частью подключения.  
  
 Если этот поток был подключен к экземпляру из Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` сопоставляется с идентификатором серверного процесса (SPID).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
