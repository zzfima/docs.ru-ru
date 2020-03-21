---
title: Функция CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176465"
---
# <a name="corexitprocess-function"></a>Функция CorExitProcess
Выключает текущий неуправляемый процесс.  
  
 Эта функция была унесена в системе .NET 4. Вместо этого используйте метод [ICLRMetaHost::ExitProcess.](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `exitCode`  
 Неисчер, оговаривает код выхода процесса.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Начиная с .NET Framework `CorExitProcess` 4, выходы из каждого запущенного времени выполнения в процессе, а не только время выполнения, к которому были связаны устаревшие AI.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
