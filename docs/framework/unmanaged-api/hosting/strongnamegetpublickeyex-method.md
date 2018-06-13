---
title: Метод StrongNameGetPublicKeyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03e3ff2adc238640034309e0f9eab6e786472631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446097"
---
# <a name="strongnamegetpublickeyex-method"></a>Метод StrongNameGetPublicKeyEx
Возвращает открытый ключ из пары открытого и закрытого ключей и указывает хэш-алгоритм и алгоритм подписи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzKeyContainer`  
 [in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей. Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае `StrongNameGetPublicKeyEx` метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.  
  
 Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).  
  
 Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания. Другие типы ключей не поддерживаются в данный момент.  
  
 `pbKeyBlob`  
 [in] Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданные Win32 `CryptExportKey` функции. Если `pbKeyBlob` равен null, контейнер ключей, заданные `szKeyContainer` должна содержать пары ключей.  
  
 `cbKeyBlob`  
 [in] Размер в байтах для `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 [out] Возвращаемый открытый ключ большого двоичного ОБЪЕКТА. `ppbPublicKeyBlob` Параметра выделяется средой CLR и возвращается вызывающему. Вызывающий объект должен освободить память с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.  
  
 `pcbPublicKeyBlob`  
 [out] Размер возвращаемого BLOB-объект открытого ключа.  
  
 `uHashAlgId`  
 [in] Хэш-алгоритм сборки. Список допустимых значений см.  
  
 `uReserved`  
 [in] Зарезервировано для будущего использования; значение по умолчанию null.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="remarks"></a>Примечания  
 Открытый ключ содержится в [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) структуры.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице показаны набор допустимых значений для `uHashAlgId` параметра.  
  
|name|Значение|  
|----------|-----------|  
|Нет|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384.|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [Структура PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [Метод StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
