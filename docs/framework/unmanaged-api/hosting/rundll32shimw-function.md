---
title: Функция RunDll32ShimW
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18247a947449ea5fd19f1882031b598086332742
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441744"
---
# <a name="rundll32shimw-function"></a>Функция RunDll32ShimW
Выполняет указанную команду.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hwnd`  
 [in] Дескриптор окна, в котором будет отображаться выходные данные команды.  
  
 `hinst`  
 [in] Дескриптор в библиотеку, содержащую команду.  
  
 `lpszCmdLine`  
 [in] Строка, указывающая команду для выполнения.  
  
 `nCmdShow`  
 [in] Целое число, определяющее режим отображения в окне вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
