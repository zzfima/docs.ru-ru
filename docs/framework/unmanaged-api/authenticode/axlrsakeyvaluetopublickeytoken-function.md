---
title: Функция _AxlRSAKeyValueToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 1f53df33a65d3f75b7574eda3507e370c2e086ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099820"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a>\_функция Акслрсакэйвалуетопубликкэйтокен

Преобразует модули и экспоненту в строгое имя маркера открытого ключа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pModulusBlob`  
 окне Большой двоичный объект модуля в кодировке Base64 (из элемента > модуля \<).  См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `pExponentBlob`  
 окне Большой двоичный объект экспоненты в кодировке Base64 (из элемента \<Экспоненты >). См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `ppwszPublicKeyToken`  
 [из] Указатель на WCHAR * для получения шестнадцатеричного кодированного маркера открытого ключа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.  
  
## <a name="see-also"></a>См. также

- [Authenticode](index.md)
