---
title: Функция CertVerifyAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06f69bf867b565edbab06dadb32e5377357e91f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617684"
---
# <a name="certverifyauthenticodelicense-function"></a>Функция CertVerifyAuthenticodeLicense
Проверяет правильность лицензии Authenticode XrML.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pLicenseBlob`  
 [в] Лицензия Authenticode XrML должна быть проверена.  
  
 См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.  
  
 `dwFlags`  
 [в] Необязательно. Комбинация следующих значений:  
  
- AXL_REVOCATION_NO_CHECK  
  
- AXL_REVOCATION_CHECK_END_CERT_ONLY  
  
- AXL_REVOCATION_CHECK_ENTIRE_CHAIN  
  
- AXL_URL_CACHE_ONLY_RETRIEVAL  
  
- AXL_LIFETIME_SIGNING  
  
- AXL_TRUST_MICROSOFT_ROOT_ONLY  
  
 `pSignerInfo`  
 [из] Для получения сведений о подписавшем. Если лицензия не подписана, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE. Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) функции после использования.  
  
 См. в разделе [структура AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).  
  
 `pTimestamperInfo`  
 [из] Для получения сведений об отметке времени (если есть). Если отметки времени для лицензии не установлены, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE. Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) функции после использования.  
  
 См. в разделе [структура AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение `S_OK` в случае успешного выполнения. В противном случае возвращается код ошибки.  
  
## <a name="see-also"></a>См. также

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [Метод GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
