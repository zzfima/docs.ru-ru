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
ms.openlocfilehash: f0b30cc2c499644ffc97a734e1554e4e352b34af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431894"
---
# <a name="coeeshutdowncom-function"></a>Функция CoEEShutDownCOM
Принудительно общеязыковой среды выполнения (CLR), чтобы освободить все указатели на интерфейс, содержащиеся внутри вызываемых оболочек времени выполнения (RCW). Это приводит к по освобождению всех кэшей вызываемой оболочки времени Выполнения. Рекомендуется использовать эту глобальную функцию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Вместо этого используйте точку входа для конкретной среде выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Примечания  
 `CoEEShutDownCOM` Функция сначала освобождает все оболочки RCW во всех контекстах и всех кэшах, а затем удаляет все уведомления завершаемые, существующих в программе установки. Выгрузка DLL не выполнена.  
  
> [!CAUTION]
>  Эта функция затрагивает все среды выполнения, загруженные в процесс.  
  
 Начиная с версии [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], вызовите точку входа для этой функции в конкретной среде выполнения, который требуется изменить. Чтобы получить точку входа, вызовите [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) метод и укажите «CoEEShutDownCOM».  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
