---
title: Метод ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176322"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>Метод ICLRStrongName::StrongNameTokenFromPublicKey
Получает маркер, представляющий открытый ключ. Сильный маркер имени — это укороченная форма клавиши общего пользования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbPublicKeyBlob`  
 (в) Структура типа [PublicKeyBlob,](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) содержащая публичную часть ключевой пары, используемой для создания сильной подписи имен.  
  
 `cbPublicKeyBlob`  
 (в) Размер, в байтах, из `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 (ваут) Сильное имя маркер, соответствующий `pbPublicKeyBlob`ключу прошло в . Общее время выполнения языка выделяет память, в которой возвращается токен. Звонящее должно освободить эту память с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
  
 `pcbStrongNameToken`  
 (ваут) Размер, в байтах, возвращенного сильного маркера имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  
 Сильный маркер имени — это укороченная форма общедоступного ключа, которая используется для экономии места при хранении ключевой информации в метаданных. В частности, сильные маркеры имен используются в ссылках на сборку для обозначения зависимой сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** Включено в качестве ресурса в mscoree.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Структура PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
