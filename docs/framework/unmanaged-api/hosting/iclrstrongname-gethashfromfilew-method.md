---
title: Метод ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acfa5c138faa47c96600530ab923de102b173ed6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672738"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>Метод ICLRStrongName::GetHashFromFileW
Создает хэш содержимого файла, указанного строкой Юникода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Имя файла для хеширования Юникода.  
  
 `piHashAlg`  
 [in, out] Алгоритм, используемый при создании хеша. Допустимыми являются алгоритмы, определенные интерфейсом Win32 CryptoAPI. Если `piHashAlg` имеет значение 0, CALG_SHA 1 используется алгоритм по умолчанию.  
  
 `pbHash`  
 [out] Массив байтов, содержащий созданный хэш.  
  
 `cchHash`  
 [in] Максимальный размер буфера, на которые указывают `pbHash`.  
  
 `pchHash`  
 [out] Размер в байтах из `pbHash`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="remarks"></a>Примечания  
 Этот метод является таким же, как [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) , за исключением того, что спецификация имени файла является Юникода вместо ANSI.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
