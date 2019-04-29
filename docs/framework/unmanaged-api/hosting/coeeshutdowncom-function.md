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
ms.openlocfilehash: 8ddef35b1b707cc5c962402e880923dca7d4d9d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789653"
---
# <a name="coeeshutdowncom-function"></a>Функция CoEEShutDownCOM
Заставляет общеязыковой среды выполнения (CLR), чтобы освободить все указатели на интерфейс, содержащиеся внутри вызываемых оболочек времени выполнения (RCW). Это приводит к по освобождению всех кэшей вызываемой оболочки времени Выполнения. Это глобальная функция является устаревшей в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Вместо этого используйте точку входа для конкретной среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Примечания  
 `CoEEShutDownCOM` Функция сначала освобождает все оболочки RCW во всех контекстах и всех кэшах, а затем удаляет все уведомления демонтажа, существующие в программе установки. Выгрузка DLL не выполнена.  
  
> [!CAUTION]
>  Эта функция влияет на все среды выполнения, которые загружаются в процесс.  
  
 Начиная с версии [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], вызова точки входа для этой функции в конкретной среде выполнения, необходимо провести эксперимент. Чтобы получить точку входа, вызовите [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) метод и указать «CoEEShutDownCOM».  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
