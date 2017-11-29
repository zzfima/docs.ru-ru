---
title: "Функция _CorExeMain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: _CorExeMain
helpviewer_keywords: _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c341d578a45d72804d9ac33e2aefe513fd33922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corexemain-function"></a>Функция _CorExeMain
Инициализирует общеязыковой среды выполнения (CLR), находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция вызывается загрузчиком в процессах, созданных из управляемых сборок исполняемый файл. DLL-сборки, загрузчик вызывает [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) вместо этого функцию.  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле образа.  
  
 В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorExeMain` функция косвенно через адресную привязку в загрузчик операционной системы. Во всех других версиях Windows он вызывается загрузчиком операционной системы.  
  
 Дополнительные сведения см. в разделе «Примечания» в [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
