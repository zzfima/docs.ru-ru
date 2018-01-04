---
title: "Метод IMetaDataEmit::DefineTypeRefByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>Метод IMetaDataEmit::DefineTypeRefByName
Получает маркер метаданных для типа, определенного в указанной области, которое находится за пределами текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tkResolutionScope`  
 [in] Токен, указывая область разрешения. Допустимы следующие типы токенов:  
  
-   `mdModuleRef`, если тип определен в той же сборке, в которой определен вызывающий объект.  
  
-   `mdAssemblyRef`, если тип определен в сборке, отличной от той, в которой определен вызывающий объект.  
  
-   `mdTypeRef`, если тип является вложенным типом.  
  
-   `mdModule`, если тип определен в том же модуле, в котором определен вызывающий объект.  
  
-   Значение NULL, если тип определен глобально.  
  
 `szName`  
 [in] Имя типа целевого объекта в формате Юникод.  
  
 `ptr`  
 [out] Указатель на `mdTypeRef` маркер, который назначен тип.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
