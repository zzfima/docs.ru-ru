---
title: Метод ICLRStrongName::StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5bb3d48d33333e888200bc607d3a193482f0336
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433657"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a>Метод ICLRStrongName::StrongNameTokenFromAssemblyEx
Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ, представляющий маркер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Путь к файлу переносимого исполняемого (PE) для сборки.  
  
 `ppbStrongNameToken`  
 [out] Возвращаемый строгое имя маркера.  
  
 `pcbStrongNameToken`  
 [out] Размер в байтах строгое имя маркера.  
  
 `ppbPublicKeyBlob`  
 [out] Возвращаемый открытый ключ.  
  
 `pcbPublicKeyBlob`  
 [out] Размер в байтах для открытого ключа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="remarks"></a>Примечания  
 Маркер строгого имени — это сокращенная форма открытого ключа. Маркер является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки. Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.  
  
 После получения ключа и создания маркера, необходимо вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
