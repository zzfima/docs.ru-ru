---
title: Функция _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f62ad2c9ec6e1c9672ac5c78e838e926b02359f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512376"
---
# <a name="cordllmain-function"></a>Функция _CorDllMain
Инициализирует общеязыковой среды выполнения (CLR), размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.  
  
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
 [in] Указывает, почему вызывается функция точки входа библиотеки DLL. Этот параметр может принимать одно из следующих значений: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH или DLL_PROCESS_DETACH. Описание этих значений, см. в разделе `DllMain` документации пакета Platform SDK.  
  
 `lpReserved`  
 [in] Не используется.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `true` для достижения успеха и `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Эта функция вызывается загрузчиком операционной системы для DLL-сборки. Исполняемые сборки, загрузчик вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) вместо этого функцию.  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.  
  
 В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorDllMain` функция вызывается косвенно через fixupin загрузчик операционной системы. Во всех других версиях Windows он вызывается загрузчиком операционной системы.  
  
 Дополнительные сведения см. в разделе "Примечания" в [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
