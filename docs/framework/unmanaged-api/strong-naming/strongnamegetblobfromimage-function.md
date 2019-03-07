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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c9f53c1d0c06498c6c9cede938d115f38a47569
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478795"
---
# <a name="strongnamegetblobfromimage-function"></a>Функция StrongNameGetBlobFromImage
Получает двоичное представление образа сборки по указанному адресу памяти.  
  
 Эта функция является устаревшей. Используйте [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbBase`  
 [in] Адрес памяти, сопоставленной сборки манифеста.  
  
 `dwLength`  
 [in] Размер в байтах, изображения в `pbBase`.  
  
 `pbBlob`  
 [in] Буфер, содержащий двоичное представление изображения.  
  
 `pcbBlob`  
 [in, out] Максимальный размер в байтах, запрошенную `pbBlob`. По возвращении фактический размер в байтах из `pbBlob`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` После успешного выполнения; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Если `StrongNameGetBlobFromImage` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** StrongName.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [Метод StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
