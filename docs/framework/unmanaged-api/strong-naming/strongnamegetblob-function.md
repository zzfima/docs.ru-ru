---
title: Функция StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7892f87e4e4001dc6ba66a00becb0e7af2dc9cb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamegetblob-function"></a>Функция StrongNameGetBlob
Заполняет указанный буфер двоичное представление исполняемого файла по указанному адресу.  
  
 Эта функция устарела. Используйте [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) метод вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Допустимый путь к исполняемому файлу для загрузки.  
  
 `pbBlob`  
 [in] Буфер, в которой для загрузки исполняемого файла.  
  
 `pcbBlob`  
 [in, out] Максимальный размер в байтах, запрошена `pbBlob`. По возвращении фактический размер в байтах для `pbBlob`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` При успешном завершении; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Если `StrongNameGetBlob` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [Метод StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
