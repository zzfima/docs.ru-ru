---
title: "Функция StrongNameSignatureSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureSize
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureSize
helpviewer_keywords: StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7944763f1c1379228e715b18b563e7aa776fedac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturesize-function"></a>Функция StrongNameSignatureSize
Возвращает размер подписи строгого имени. `StrongNameSignatureSize`обычно используется компиляторами, чтобы определить, сколько места для резервирования в файле, при создании сборки с отложенной подписью.  
  
 Эта функция устарела. Используйте [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) метод вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `pbPublicKeyBlob`  
 [in] Структура типа [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемой для создания подписи строгого имени.  
  
 `cbPublicKeyBlob`  
 [in] Размер в байтах для `pbPublicKeyBlob`.  
  
 `pcbSize`  
 [in] Число байтов, необходимое для хранения подписи строгого имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Если `StrongNameSignatureSize` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)  
 [Iclrstrongname-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
