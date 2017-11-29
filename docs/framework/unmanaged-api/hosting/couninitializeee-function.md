---
title: "Функция CoUninitializeEE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeEE
helpviewer_keywords: CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d64064c29d2a03578305f71a37e759907814727e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="couninitializeee-function"></a>Функция CoUninitializeEE
`CoUninitializeEE`является устаревшим и не добавляет новых функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Примечания  
 Исполняющий механизм среды выполнения не может быть выгружен из процесса. Завершение работы ядра выполнения следует вызвать [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).  
  
## <a name="see-also"></a>См. также  
 [Coinitializeee-функция](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
