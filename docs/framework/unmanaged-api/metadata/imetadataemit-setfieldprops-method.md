---
title: Метод IMetaDataEmit::SetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097659"
---
# <a name="imetadataemitsetfieldprops-method"></a>Метод IMetaDataEmit::SetFieldProps
Задает или обновляет значение по умолчанию для поля, который ссылается токен указанного поля.  
  
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
  
## <a name="parameters"></a>Параметры  
 `fd`  
 [in] Маркер целевого поля.  
  
 `dwFieldFlags`  
 [in] Атрибуты поля. Это битовая маска `CorFieldAttr` значения.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** Для постоянного значения. Это `CorElementType` значение. Если не определяется константой, это значение равно `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Постоянное значение для поля.  
  
 `cchValue`  
 [in] Размер в символы Юникода из `pValue`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
