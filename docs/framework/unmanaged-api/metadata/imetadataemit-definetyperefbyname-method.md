---
title: Метод IMetaDataEmit::DefineTypeRefByName
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4fd6102b65137a06009428c1245b80c0d44924a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445495"
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
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
