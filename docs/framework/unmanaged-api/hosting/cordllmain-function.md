---
title: "Функция _CorDllMain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 985f2284026054217671de767c316b1fba35c098
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordllmain-function"></a>Функция _CorDllMain
Инициализирует общеязыковой среды выполнения (CLR), находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hInst`  
 [in] Дескриптор экземпляра загруженного модуля.  
  
 `dwReason`  
 [in] Указывает, почему вызывается функция точки входа DLL. Этот параметр может принимать одно из следующих значений: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH или DLL_PROCESS_DETACH. Описание этих значений см. в разделе `DllMain` документации пакета Platform SDK.  
  
 `lpReserved`  
 [in] Не используется.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `true` успеха и `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Эта функция вызывается загрузчиком операционной системы для DLL-сборки. Для исполняемых сборок загрузчик вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) вместо этого функцию.  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в DLL-файле.  
  
 В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorDllMain` функция косвенно через fixupin загрузчик операционной системы. Во всех других версиях Windows он вызывается загрузчиком операционной системы.  
  
 Дополнительные сведения см. в разделе «Примечания» в [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
