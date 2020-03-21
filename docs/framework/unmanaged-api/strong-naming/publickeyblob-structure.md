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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176959"
---
# <a name="publickeyblob-structure"></a>Структура PublicKeyBlob
Представляет, в двоичном формате, открытый ключ публичной/ частной ключевой пары.  
  
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
  
|Участник|Описание|  
|------------|-----------------|  
|`SigAlgId`|Идентификатор алгоритма подписи (типа, `ALG_ID`как это определено в WinCrypt.h) общедоступного ключа.|  
|`HashAlgId`|Идентификатор алгоритма хэша (типа, `ALG_ID`как это определено в WinCrypt.h) общедоступного ключа.|  
|`cbPublicKey`|Длина ключа в байтах.|  
|`PublicKey`|Массив байт с переменной длиной, содержащий ключевое значение в формате, возвращенном CryptoAPI.|  
  
## <a name="remarks"></a>Remarks  
 Структура `PublicKeyBlob` используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), и другие сильные функции имя представлять общественный ключ от публичного / частного ключа пары.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Функция StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)
