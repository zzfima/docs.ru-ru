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
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176985"
---
# <a name="gethashfromfile-function"></a>Функция GetHashFromFile
Создает хэш содержимого указанного файла.  
  
 Эта функция была амортизирована. Вместо этого используйте метод [ICLRStrongName::GetHashFromFile.](../hosting/iclrstrongname-gethashfromfile-method.md)  
  
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
  
## <a name="remarks"></a>Remarks  
 Эта функция такая же, как [GetHashFromFileW](gethashfromfilew-function.md), за исключением того, что спецификация имени файла ANSI вместо Unicode.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Метод GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
