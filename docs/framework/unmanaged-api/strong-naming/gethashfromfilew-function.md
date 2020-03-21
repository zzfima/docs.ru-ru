---
title: Функция GetHashFromFileW
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175087"
---
# <a name="gethashfromfilew-function"></a>Функция GetHashFromFileW
Создает хэш содержимого файла, указанного строкой Юникода.  
  
 Эта функция была амортизирована. Вместо этого используйте метод [ICLRStrongName::GetHashFromFileW.](../hosting/iclrstrongname-gethashfromfilew-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 (в) Имя файла Unicode хэша.  
  
 `piHashAlg`  
 (в, вне) Алгоритм для использования при генерации хэша. Действительные алгоритмы определяются Win32 CryptoAPI. Если `piHashAlg` установлен до 0, используется алгоритм по умолчанию CALG_SHA-1.  
  
 `pbHash`  
 (ваут) Массив байта, содержащий генерируемый хэш.  
  
 `cchHash`  
 (в) Максимальный размер буфера, `pbHash`на который указывает .  
  
 `pchHash`  
 (ваут) Размер, в байтах, из `pbHash`.  
  
## <a name="remarks"></a>Remarks  
 Эта функция такая же, как [GetHashFromFile](gethashfromfile-function.md), за исключением того, что спецификация имени файла Unicode вместо ANSI.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Метод GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
