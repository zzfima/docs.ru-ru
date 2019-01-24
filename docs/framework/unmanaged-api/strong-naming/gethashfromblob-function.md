---
title: Функция GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfa846aa66345e23e085ca148c7e3f492c529f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576347"
---
# <a name="gethashfromblob-function"></a>Функция GetHashFromBlob
Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.  
  
 Эта функция является устаревшей. Используйте [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pbBlob`  
 [in] Указатель на адрес блока памяти, хэширование которого требуется выполнить.  
  
 `cchBlob`  
 [in] Длина в байтах блока памяти.  
  
 `piHashAlg`  
 [in, out] Константа, указывающая хэш-алгоритм. Использовать нуль для алгоритма по умолчанию.  
  
 `pbHash`  
 [out] Буфер, возвращенный хэша.  
  
 `cchHash`  
 [in] Запрошенный максимальный размер `pbHash`.  
  
 `pchHash`  
 [out] Размер в байтах, возвращаемого `pbHash`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** StrongName.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
