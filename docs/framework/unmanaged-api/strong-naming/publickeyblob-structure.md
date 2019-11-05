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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140607"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`SigAlgId`|Идентификатор алгоритма подписи (типа `ALG_ID`, как определено в Винкрипт. h) открытого ключа.|  
|`HashAlgId`|Идентификатор хэш-алгоритма (типа `ALG_ID`, как определено в Винкрипт. h) открытого ключа.|  
|`cbPublicKey`|Длина ключа в байтах.|  
|`PublicKey`|Массив байтов переменной длины, который содержит значение ключа в формате, возвращенном CryptoAPI.|  
  
## <a name="remarks"></a>Заметки  
 Структура `PublicKeyBlob` используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Функция StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)
