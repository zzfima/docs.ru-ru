---
title: Функция StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 41226cd909900bd2da7bdcf9b9a49567d3042b01
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094878"
---
# <a name="strongnamegetblobfromimage-function"></a>Функция StrongNameGetBlobFromImage
Получает двоичное представление образа сборки по указанному адресу памяти.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbBase`  
 окне Адрес сопоставленного манифеста сборки в памяти.  
  
 `dwLength`  
 окне Размер изображения в байтах, в `pbBase`.  
  
 `pbBlob`  
 окне Буфер для хранения двоичного представления изображения.  
  
 `pcbBlob`  
 [вход, выход] Запрошенный максимальный размер `pbBlob`в байтах. При возврате фактический размер (в байтах) `pbBlob`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` при успешном завершении; в противном случае `false`.  
  
## <a name="remarks"></a>Заметки  
 Если функция `StrongNameGetBlobFromImage` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [Метод StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
