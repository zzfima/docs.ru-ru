---
title: Функция GetHashFromFile
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f98f888280090bfa613acf6ae37bc60ab63c371e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456518"
---
# <a name="gethashfromfile-function"></a>Функция GetHashFromFile
Создает хэш содержимого указанного файла.  
  
 Эта функция устарела. Используйте [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) метод вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szFilePath`  
 [in] Имя файла для хеширования.  
  
 `piHashAlg`  
 [in, out] Алгоритм, используемый при создании хеша. Допустимыми являются алгоритмы, определенные интерфейсом CryptoAPI в Win32. Если `piHashAlg` имеет значение 0, алгоритм по умолчанию используется CALG_SHA-1.  
  
 `pbHash`  
 [out] Массив байтов, содержащий созданный хеш.  
  
 `cchHash`  
 [in] Максимальный размер буфера, `pbHash` указывает.  
  
 `pchHash`  
 [out] Размер в байтах, возвращаемого `pbHash`.  
  
## <a name="remarks"></a>Примечания  
 Эта функция является таким же, как [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), за исключением того, что спецификация имени файла — ANSI, а не в Юникоде.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [Метод GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
