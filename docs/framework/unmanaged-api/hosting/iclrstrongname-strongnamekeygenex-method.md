---
title: Метод ICLRStrongName::StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b02792a0547b9b8ba6215069c3c0abf48726ded
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508669"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a>Метод ICLRStrongName::StrongNameKeyGenEx
Создает новую пару открытого и закрытого ключа с заданным размером ключа, для использования строгого имени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszKeyContainer`  
 [in] Имя запрошенного контейнера ключа. `wszKeyContainer` должен быть непустой строкой или значение null, чтобы создать временное имя.  
  
 `dwFlags`  
 [in] Значение, указывающее, следует ли оставить ключ зарегистрирован. Поддерживаются следующие значения:  
  
-   0x00000000 — используется, когда `wszKeyContainer` имеет значение null, если для создания временного имени контейнера ключа.  
  
-   0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.  
  
 `dwKeySize`  
 [in] Запрошенный размер ключа в битах.  
  
 `ppbKeyBlob`  
 [out] Возвращаемый ключа пары открытого и закрытого.  
  
 `pcbKeyBlob`  
 [out] Размер в байтах из `ppbKeyBlob`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="remarks"></a>Примечания  
 Требуется .NET Framework версий 1.0 и 1.1 `dwKeySize` 1024 бит для подписи сборки строгим именем; версии 2.0 добавлена поддержка 2048-разрядные ключи.  
  
 После извлечения ключа должно вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
