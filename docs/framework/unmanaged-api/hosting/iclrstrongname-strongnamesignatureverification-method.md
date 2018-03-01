---
title: "Метод ICLRStrongName::StrongNameSignatureVerification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1d8cb0ac6c671dae6ca5985e4082e2d3e71d89e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>Метод ICLRStrongName::StrongNameSignatureVerification
Получает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени, которая будет проверена в соответствии с заданными флагами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Путь к переносимого исполняемого файла (.dll или .exe) для сборки для проверки.  
  
 `dwInFlags`  
 [in] Флаги для изменения поведения проверки. Поддерживаются следующие значения:  
  
-   `SN_INFLAG_FORCE_VER`(0x00000001) — принудительная проверка, даже если это необходимо переопределить параметры реестра.  
  
-   `SN_INFLAG_INSTALL`(0x00000002) — указывает, что в первый раз, проверка манифеста.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0x00000004) — указывает, что кэш будет предоставлять доступ только пользователям с правами администратора.  
  
-   `SN_INFLAG_USER_ACCESS`(0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.  
  
-   `SN_INFLAG_ALL_ACCESS`(0x00000010) — указывает, что кэш будет предоставляют никаких гарантий ограничения доступа.  
  
-   `SN_INFLAG_RUNTIME`(0x80000000) — зарезервировано для внутренней отладки.  
  
 `pdwOutFlags`  
 [out] Флаги, указывающее, был ли проверен подписи строгого имени. Поддерживается следующее значение:  
  
-   `SN_OUTFLAG_WAS_VERIFIED`(0x00000001) — это значение равно `false` для указания, что проверка прошла успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
