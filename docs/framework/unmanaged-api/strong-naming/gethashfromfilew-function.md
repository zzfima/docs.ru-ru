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
ms.openlocfilehash: db6f39119d143d27c0d3a80a9c65565d4dfd0d39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140674"
---
# <a name="gethashfromfilew-function"></a>Функция GetHashFromFileW
Создает хэш содержимого файла, указанного строкой Юникода.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) .  
  
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
 окне Имя файла в Юникоде для хэширования.  
  
 `piHashAlg`  
 [вход, выход] Алгоритм, используемый при формировании хэша. Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI. Если `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.  
  
 `pbHash`  
 заполняет Массив байтов, содержащий созданный хэш.  
  
 `cchHash`  
 окне Максимальный размер буфера, на который указывает `pbHash`.  
  
 `pchHash`  
 заполняет Размер `pbHash`в байтах.  
  
## <a name="remarks"></a>Заметки  
 Эта функция аналогична [GetHashFromFile](gethashfromfile-function.md), за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Метод GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
