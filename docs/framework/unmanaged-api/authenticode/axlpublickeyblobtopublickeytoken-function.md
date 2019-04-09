---
title: Функция _AxlPublicKeyBlobToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b2535441da173ee13653c68f25039fd1431261a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147437"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a>Функция _AxlPublicKeyBlobToPublicKeyToken
Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCspPublicKeyBlob`  
 [в] Большой двоичный объект открытого ключа CSP.  
  
 `ppwszPublicKeyHash`  
 [из] Указатель на WCHAR * для получения шестнадцатеричного кодированного хэша открытого ключа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если функция выполнилась успешно; в противном случае `S_FALSE`.  
  
## <a name="see-also"></a>См. также

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
