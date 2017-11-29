---
title: "Authenticode (справочник по неуправляемым интерфейсам API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e90a13ebf46f1891061c78435b7ba47d68de001d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (справочник по неуправляемым интерфейсам API)
Поддерживает модуль создания и проверки лицензий Authenticode XrML.  
  
## <a name="in-this-section"></a>Содержание  
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
 [Справочник по неуправляемым API](../../../../docs/framework/unmanaged-api/index.md)
