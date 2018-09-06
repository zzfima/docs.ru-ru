---
title: Метод ICLRStrongName::StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc5a40a0e26f116ce1700973a5000e8d6bbbd890
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732948"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a>Метод ICLRStrongName::StrongNameSignatureSize
Возвращает размер подписи строгого имени. Этот метод обычно используется компиляторами, чтобы определить, какой объем места, резервируемого в файле, при создании сборки с отложенной подписью.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `pbPublicKeyBlob`  
 [in] Структура типа [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащий открытую часть пары ключей, использованного для создания подписи строгого имени.  
  
 `cbPublicKeyBlob`  
 [in] Размер в байтах из `pbPublicKeyBlob`.  
  
 `pcbSize`  
 [in] Число байтов, необходимое для хранения подписи строгого имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
