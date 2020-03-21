---
title: Метод ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: ed735c3d7830551581df35793f3f6fdc4953dc8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178076"
---
# <a name="iclrstrongnamegethashfromfile-method"></a>Метод ICLRStrongName::GetHashFromFile
Создает хэш содержимого указанного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFilePath`  
 (в) Название файла хэшу.  
  
 `piHashAlg`  
 (в, вне) Алгоритм для использования при генерации хэша. Действительные алгоритмы определяются Win32 CryptoAPI. Если `piHashAlg` установлен до 0, используется алгоритм по умолчанию CALG_SHA-1.  
  
 `pbHash`  
 (ваут) Массив байта, содержащий генерируемый хэш.  
  
 `cchHash`  
 (в) Максимальный размер буфера, на который `pbHash` указывает.  
  
 `pchHash`  
 (ваут) Размер, в байтах, `pbHash`возвращенного .  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  
 Этот метод такой же, как [метод ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) метод, за исключением того, что спецификация имени файла ANSI вместо Unicode.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
