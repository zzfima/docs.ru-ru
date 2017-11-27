---
title: "Функция GetHistoryFileDirectory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHistoryFileDirectory
api_location: fusion.dll
api_type: DLLExport
f1_keywords: GetHistoryFileDirectory
helpviewer_keywords: GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f01100140e9e1dd05cb42b3cfe586c5f6462444c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gethistoryfiledirectory-function"></a>Функция GetHistoryFileDirectory
Возвращает путь к каталогу журнала приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wzDir`  
 [out] Буфер для хранения пути к каталогу журнала приложения.  
  
 `pdwSize`  
 [in, out] Длина буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`wzDir`или `pdwSize` имеет значение null или версия Неверная строка.|  
  
## <a name="remarks"></a>Примечания  
 При успешном завершении `pdwSize` аргумент имеет значение длины строки пути.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Библиотека:** Fusion.dll и Mscorwks.dll. Используйте Fusion.dll вместо Mscorwks.dll, чтобы целевая правильную версию платформы .NET Framework.  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [Функция NukeDownloadedCache](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
