---
title: Структура PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e66196e2bd2cb326ca3f5badc67bcf8d81e5fc3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799161"
---
# <a name="publickeyblob-structure"></a>Структура PublicKeyBlob
Представляет в двоичном формате открытый ключ пары открытого и закрытого ключей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`SigAlgId`|Идентификатор для алгоритма подписи (типа `ALG_ID`, как определено в винкрипт. h) открытого ключа.|  
|`HashAlgId`|Идентификатор для хэш-алгоритма (типа `ALG_ID`, как определено в винкрипт. h) открытого ключа.|  
|`cbPublicKey`|Длина ключа в байтах.|  
|`PublicKey`|Массив байтов переменной длины, который содержит значение ключа в формате, возвращенном CryptoAPI.|  
  
## <a name="remarks"></a>Примечания  
 Структура `PublicKeyBlob` используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Функция StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)
