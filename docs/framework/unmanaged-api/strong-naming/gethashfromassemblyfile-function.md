---
title: Функция GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 866b34acae333f043d8e13f4d0ebd55f32046334
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140728"
---
# <a name="gethashfromassemblyfile-function"></a>Функция GetHashFromAssemblyFile
Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFilePath`  
 окне Путь к файлу для хэширования.  
  
 `piHashAlg`  
 [вход, выход] Константа, указывающая хэш-алгоритм. Для алгоритма хэширования по умолчанию используется нуль.  
  
 `pbHash`  
 заполняет Возвращаемый буфер хэша.  
  
 `cchHash`  
 окне Запрошенный максимальный размер `pbHash`.  
  
 `pchHash`  
 заполняет Возвращаемый размер `pbHash`в байтах.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [Метод GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
