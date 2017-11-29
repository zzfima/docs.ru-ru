---
title: "Функция InitDbgTransportManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: InitDbgTransportManager
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f9f637589666af3723f11eb1f828d00be57793e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="initdbgtransportmanager-function"></a>Функция InitDbgTransportManager
Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Выполнено.  
  
 E_OUTOFMEMORY  
 Функции не удалось выделить память для диспетчера транспорта.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Версии платформы .NET framework:** 3.5 SP1
