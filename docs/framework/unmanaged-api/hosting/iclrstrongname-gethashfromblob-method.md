---
title: Метод ICLRStrongName::GetHashFromBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: b42079d138e754996470e07b884d49c1ebb625c3
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901169"
---
# <a name="iclrstrongnamegethashfromblob-method"></a>Метод ICLRStrongName::GetHashFromBlob
Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbBlob`  
 окне Указатель на адрес блока памяти, который необходимо хэшировать.  
  
 `cchBlob`  
 окне Длина блока памяти в байтах.  
  
 `piHashAlg`  
 [вход, выход] Константа, указывающая хэш-алгоритм. Используйте нуль для алгоритма по умолчанию.  
  
 `pbHash`  
 заполняет Возвращаемый буфер хэша.  
  
 `cchHash`  
 окне Запрошенный максимальный размер `pbHash`.  
  
 `pchHash`  
 заполняет Размер возвращаемого `pbHash`в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
