---
title: Метод IMetaDataEmit::DefineMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad2b3e5c452a5fc79e7a1cc0342cfc1d119a5fbd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481993"
---
# <a name="imetadataemitdefinememberref-method"></a>Метод IMetaDataEmit::DefineMemberRef
Определяет ссылку на член модуля вне текущей области и получает маркер для этого определения ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tkImport`  
 [in] Маркер для целевого члена класса или интерфейса, если элемент не является общим; Если элемент является глобальным, `mdModuleRef` маркеров для других файла.  
  
 `szName`  
 [in] Имя целевого элемента.  
  
 `pvSigBlob`  
 [in] Сигнатура целевого элемента.  
  
 `cbSigBlob`  
 [in] Число байт в `pvSigBlob`.  
  
 `pmr`  
 [out] `mdMemberRef` Маркер, назначенный.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
