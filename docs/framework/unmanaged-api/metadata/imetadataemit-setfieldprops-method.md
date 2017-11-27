---
title: "Метод IMetaDataEmit::SetFieldProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f031e79deab57184043eaa44d2d8a3d369187c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldprops-method"></a>Метод IMetaDataEmit::SetFieldProps
Задает или обновляет значение по умолчанию для поля ссылается маркер указанного поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fd`  
 [in] Токен для целевого поля.  
  
 `dwFieldFlags`  
 [in] Атрибуты поля. Это битовая маска `CorFieldAttr` значения.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_`  *\**  Для постоянного значения. Это `CorElementType` значение. Если константа не определен, это значение равно `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Постоянное значение для поля.  
  
 `cchValue`  
 [in] Размер в символы Юникода из `pValue`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
