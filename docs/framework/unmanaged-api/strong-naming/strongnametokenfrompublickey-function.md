---
title: Функция StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175061"
---
# <a name="strongnametokenfrompublickey-function"></a>Функция StrongNameTokenFromPublicKey
Получает маркер, представляющий открытый ключ. Сильный маркер имени — это укороченная форма клавиши общего пользования.  
  
 Эта функция была амортизирована. Вместо этого используйте метод [ICLRStrongName::StrongNameTokenFromPublicKey.](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbPublicKeyBlob`  
 (в) Структура типа [PublicKeyBlob,](publickeyblob-structure.md) содержащая публичную часть ключевой пары, используемой для создания сильной подписи имен.  
  
 `cbPublicKeyBlob`  
 (в) Размер, в байтах, из `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 (ваут) Сильное имя маркер, соответствующий `pbPublicKeyBlob`ключу прошло в . Общее время выполнения языка выделяет память, в которой возвращается токен. Звонящее должно освободить эту память с помощью функции [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)  
  
 `pcbStrongNameToken`  
 (ваут) Размер, в байтах, возвращенного сильного маркера имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`при успешном завершении; в `false`противном случае, .  
  
## <a name="remarks"></a>Remarks  
 Сильный маркер имени — это укороченная форма общедоступного ключа, используемого для экономии места при хранении ключевой информации в метаданных. В частности, сильные маркеры имен используются в ссылках на сборку для обозначения зависимой сборки.  
  
 Если `StrongNameTokenFromPublicKey` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** Включено в качестве ресурса в mscoree.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Метод StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Структура PublicKeyBlob](publickeyblob-structure.md)
