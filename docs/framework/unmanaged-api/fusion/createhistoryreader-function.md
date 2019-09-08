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
ms.openlocfilehash: 2710d14d6e73879fd17a6b58659463ea205f2384
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795365"
---
# <a name="createhistoryreader-function"></a>Функция CreateHistoryReader
Создает средство чтения журнала для указанного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `wzFilePath`  
 окне Путь к файлу.  
  
 `ppHistoryReader`  
 заполняет При успешном завершении содержит указатель на средство чтения журнала.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError. h, а также значения, описанные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Указывает, что метод успешно завершен.|  
|E_INVALIDARG|Указывает, `wzFilePath` что `ppHistoryReader` или задана пустая ссылка.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Библиотечная** Fusion. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
