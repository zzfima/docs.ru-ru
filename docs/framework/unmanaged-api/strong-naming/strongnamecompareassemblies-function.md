---
title: Функция StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0c2e8e46c7bb3a5e693c9ea16e6c5a0722b1898
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799148"
---
# <a name="strongnamecompareassemblies-function"></a>Функция StrongNameCompareAssemblies
Определяет, отличаются ли две сборки только подписями строгого имени.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszAssembly1`  
 окне Путь к первой сборке.  
  
 `wszAssembly2`  
 окне Путь к второй сборке.  
  
 `pdwResult`  
 заполняет Одно из следующих значений:  
  
- `SN_CMP_DIFFERENT`(0) — указывает, что сборки содержат различные данные.  
  
- `SN_CMP_IDENTICAL`(1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.  
  
- `SN_CMP_SIGONLY`(2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае —. `false`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Примечания  
 Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.  
  
 Если функция `StrongNameCompareAssemblies` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
