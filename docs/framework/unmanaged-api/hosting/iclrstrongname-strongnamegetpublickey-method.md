---
title: Метод ICLRStrongName::StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181937"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>Метод ICLRStrongName::StrongNameGetPublicKey
Получает открытый ключ от публичной/частной ключевой пары. Ключевая пара может поставляться либо в качестве ключевого имени контейнера в рамках криптографического поставщика услуг (CSP), либо в виде сырой коллекции байтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szKeyContainer`  
 (в) Название ключевого контейнера, содержащего публичную/частную ключевую пару. Если `pbKeyBlob` он `szKeyContainer` недействителен, необходимо указать действительный контейнер в рамках CSP. В этом случае метод [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) извлекает общедоступный ключ из пары ключей, хранящейся в контейнере.  
  
 Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).  
  
 Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей. В настоящее время никакие другие типы ключей не поддерживаются.  
  
 `pbKeyBlob`  
 (в) Указатель на публичную/частную ключевую пару. Эта пара находится в формате, `CryptExportKey` созданном функцией Win32. Если `pbKeyBlob` он недействителен, `szKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.  
  
 `cbKeyBlob`  
 (в) Размер, в байтах, из `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 (ваут) Вернулся общественный ключ BLOB. Параметр `ppbPublicKeyBlob` выделяется общим временем выполнения языка и возвращается вызывающему. Звонящее должно освободить память с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
  
 `pcbPublicKeyBlob`  
 (ваут) Размер возвращенного публичного ключа BLOB.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  
 Открытый ключ содержится в структуре [PublicKeyBlob.](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Структура PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
