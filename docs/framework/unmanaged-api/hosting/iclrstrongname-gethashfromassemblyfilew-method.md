---
title: Метод ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7686a84759f8ac40a123d2c9a7b8f1b9b8096cb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749922"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a>Метод ICLRStrongName::GetHashFromAssemblyFileW
Создает хэш содержимого файла, указанного строкой Юникода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Путь к файлу, хэширование которого требуется выполнить. Этот параметр должен быть строкой Юникода.  
  
 `piHashAlg`  
 [in, out] Константа, указывающая хэш-алгоритм. Использовать нуль для хэш-алгоритм по умолчанию.  
  
 `pbHash`  
 [out] Буфер, возвращенный хэша.  
  
 `cchHash`  
 [in] Запрошенный максимальный размер `pbHash`.  
  
 `pchHash`  
 [out] Размер в байтах, возвращенное `pbHash`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
