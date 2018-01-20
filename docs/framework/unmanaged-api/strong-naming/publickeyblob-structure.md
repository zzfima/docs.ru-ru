---
title: "Структура PublicKeyBlob"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1f04c692b7549c4d7d8d431591eeb867b673d9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="publickeyblob-structure"></a>Структура PublicKeyBlob
Представляет открытый ключ из пары открытого и закрытого ключей в двоичном формате.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`SigAlgId`|Идентификатор алгоритма подписи (типа `ALG_ID`, как определено в WinCrypt.h) открытого ключа.|  
|`HashAlgId`|Идентификатор для хэш-алгоритм (типа `ALG_ID`, как определено в WinCrypt.h) открытого ключа.|  
|`cbPublicKey`|Длина ключа в байтах.|  
|`PublicKey`|Массив байтов переменной длины, содержащий значение ключа в формате, возвращенном CryptoAPI.|  
  
## <a name="remarks"></a>Примечания  
 `PublicKeyBlob` Структура используется [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)и другие функции строгого имени, представляющих открытый ключ из пары открытого и закрытого ключей.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [Функция StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [Структуры строгого именования](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
