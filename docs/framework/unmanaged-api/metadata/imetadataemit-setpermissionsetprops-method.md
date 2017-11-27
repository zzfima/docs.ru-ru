---
title: "Метод IMetaDataEmit::SetPermissionSetProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5666daff143d261160bb90bf31c98d1e1b7ce270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>Метод IMetaDataEmit::SetPermissionSetProps
Задает или обновляет подпись метаданных для набора разрешений, определенных во время предыдущего вызова для функции [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tk`  
 [in] Токен метаданных, представляющий объект параметризация.  
  
 `dwAction`  
 [in] Объект [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) значение, указывающее тип декларативной безопасности для использования.  
  
 `pvPermission`  
 [in] Разрешение большого двоичного ОБЪЕКТА.  
  
 `cbPermission`  
 [in] Размер в байтах для `pvPermission`.  
  
 `ppm`  
 [out] `mdPermission` Токен метаданных, представляющий обновленные разрешения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
