---
title: Функция CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3a3cc21dbbcfa99ddcecb534bd2e337da005597
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="createhistoryreader-function"></a>Функция CreateHistoryReader
Создает средство чтения журнала для указанного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a>Параметры  
 `wzFilePath`  
 [in] Путь к файлу.  
  
 `ppHistoryReader`  
 [out] При успешном завершении содержит указатель на чтения журнала.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, помимо значений, описанных в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Указывает на успешное завершение метода.|  
|E_INVALIDARG|Указывает, что `wzFilePath` или `ppHistoryReader` присваивается указатель null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Библиотека:** Fusion.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
