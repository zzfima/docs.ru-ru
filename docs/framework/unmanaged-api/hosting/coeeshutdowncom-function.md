---
title: Функция CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 164384f043a1722ace6e5c4098cb31c4327cba1e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044063"
---
# <a name="coeeshutdowncom-function"></a>Функция CoEEShutDownCOM
Заставляет общеязыковую среду выполнения (CLR) освобождать все указатели интерфейсов, содержащиеся внутри вызываемых оболочек времени выполнения (RCW). Это приведет к освобождению всех кэшей RCW. Эта глобальная функция является устаревшей в .NET Framework 4. Вместо этого используйте точку входа для конкретной среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Примечания  
 `CoEEShutDownCOM` Функция сначала освобождает все вызываемые оболочки RCW во всех контекстах и во всех кэшах, а затем удаляет все уведомления о разрыве, существующие в программе установки. Выгрузка библиотек DLL не выполняется.  
  
> [!CAUTION]
> Эта функция влияет на все среды выполнения, загруженные в процесс.  
  
 Начиная с .NET Framework 4, вызовите точку входа для этой функции в конкретной среде выполнения, которую необходимо изменить. Чтобы получить точку входа, вызовите метод [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) и укажите "коишутдовнком".  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** COR. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
