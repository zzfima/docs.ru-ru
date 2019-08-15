---
title: Функция CertTimestampAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c2bb6f0324c461f59bd98a70333b176e79a16a6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039596"
---
# <a name="certtimestampauthenticodelicense-function"></a>Функция CertTimestampAuthenticodeLicense
Отметки времени для лицензии Authenticode XrML.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pSignedLicenseBlob`  
 [в] Подписанная лицензия Authenticode XrML, требующая отметки времени. См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `pwszTimestampURI`  
 [в] URL-адресу сервера отметок времени.  
  
 `pTimestampSignatureBlob`  
 [из] Указатель на CRYPT_DATA_BLOB для получения подписи с отметкой времени в кодировке base64. Его `pTimestampSignatureBlob` можно бесплатно -> `pbData` использовать послеиспользования.`HepFree()` См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
## <a name="remarks"></a>Примечания  
 Подпись с отметкой времени фактически представляет собой сообщение PKCS #7 SignedData, содержимое которого является двоичной формой SignatureValue из подписи лицензии. По сути, она действует как подпись, подтверждающая лицензию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.  
  
## <a name="see-also"></a>См. также

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
