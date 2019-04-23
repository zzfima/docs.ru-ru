---
title: Authenticode (справочник по неуправляемым интерфейсам API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408219307015d5c39cb581b3884ed9810f4c0566
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216357"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (справочник по неуправляемым интерфейсам API)
Поддерживает модуль создания и проверки лицензий Authenticode XrML.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Функция _AxlGetIssuerPublicKeyHash](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.  
  
 [Функция _AxlPublicKeyBlobToPublicKeyToken](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.  
  
 [Функция _AxlRSAKeyValueToPublicKeyToken](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 Преобразует модули и экспоненту в строгое имя маркера открытого ключа.  
  
 [Функция CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 Освобождает ресурсы, выделенные для структуры AXL_AUTHENTICODE_SIGNER_INFO.  
  
 [Функция CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 Освобождает ресурсы, выделенные для структуры AXL_AUTHENTICODE_TIMESTAMPER_INFO.  
  
 [Функция CertTimestampAuthenticodeLicense](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 Присваивает метки времени лицензии Authenticode XrML, созданной функцией CertCreateAuthenticodeLicense.  
  
 [Функция CertVerifyAuthenticodeLicense](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 Проверяет правильность лицензии Authenticode XrML.  
  
 [Структура AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 Определяет информацию о подписавшем Authenticode.  
  
 [Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 Определяет информацию об отметке времени Authenticode.  
  
## <a name="see-also"></a>См. также

- [Справочник по неуправляемым API](../../../../docs/framework/unmanaged-api/index.md)
