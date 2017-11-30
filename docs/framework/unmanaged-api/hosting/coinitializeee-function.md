---
title: "Функция CoInitializeEE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeEE
helpviewer_keywords: CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 429d055ec0853d04f794b063a76a395d98aceb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="coinitializeee-function"></a>Функция CoInitializeEE
Обеспечивает загрузку исполняющий механизм среды выполнения в процесс. Эта функция устарела в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fFlags`  
 [in] Один из [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) константы перечисления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, определенные в файле Winerror.h и значения в таблице ниже.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Подсистема выполнения была успешно загружена.|  
|S_FALSE|Подсистема выполнения уже загружен.|  
|E_FAIL|Не удалось загрузить подсистему выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод загружает ядро выполнения, если он не был загружен ранее.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
