---
title: Метод IMetaDataEmit::SetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82675af85f049aeb288b3dcc18f222c0387a37b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050107"
---
# <a name="imetadataemitsetfieldmarshal-method"></a>Метод IMetaDataEmit::SetFieldMarshal
Задает сведения о маршалинге для параметра поля, возвращаемого значения метода или метода ссылается указанный токен PInvoke.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 [in] Токен для целевого элемента данных. Это может быть либо `mdFieldDef` или `mdParamDef` токена.  
  
 `pvNativeType`  
 [in] Сигнатура для неуправляемого типа.  
  
 `cbNativeType`  
 [in] Число байт в `pvNativeType`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
