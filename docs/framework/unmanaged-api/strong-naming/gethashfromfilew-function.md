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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799195"
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
 [вход, выход] Алгоритм, используемый при формировании хэша. Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI. Если `piHashAlg` параметр имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.  
  
 `pbHash`  
 заполняет Массив байтов, содержащий созданный хэш.  
  
 `cchHash`  
 окне Максимальный размер буфера, `pbHash`на который указывает.  
  
 `pchHash`  
 заполняет Размер (в байтах `pbHash`).  
  
## <a name="remarks"></a>Примечания  
 Эта функция аналогична [GetHashFromFile](gethashfromfile-function.md), за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Метод GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
