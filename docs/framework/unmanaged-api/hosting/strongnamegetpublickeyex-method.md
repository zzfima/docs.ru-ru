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
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176231"
---
# <a name="strongnamegetpublickeyex-method"></a>Метод StrongNameGetPublicKeyEx
Получает общедоступный ключ от публичной/частной пары ключей и определяет алгоритм хэша и алгоритм подписи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="parameters"></a>Параметры  
 `pwzKeyContainer`  
 (в) Название ключевого контейнера, содержащего публичную/частную ключевую пару. Если `pbKeyBlob` он `szKeyContainer` недействителен, необходимо указать действительный контейнер в рамках поставщика криптографических услуг (CSP). В этом случае `StrongNameGetPublicKeyEx` метод извлекает общедоступный ключ из пары ключей, хранящейся в контейнере.  
  
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
  
 `uHashAlgId`  
 (в) Алгоритм хэша сборки. Список принятых значений можно осмотреть в разделе «Замечания».  
  
 `uReserved`  
 (в) Зарезервировано для использования в будущем; по умолчанию свести на нет.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  
 Открытый ключ содержится в структуре [PublicKeyBlob.](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
  
## <a name="remarks"></a>Remarks  
 В следующей таблице показан набор принятых значений `uHashAlgId` для параметра.  
  
|Имя|Значение|  
|----------|-----------|  
|None|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Структура PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Метод StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
