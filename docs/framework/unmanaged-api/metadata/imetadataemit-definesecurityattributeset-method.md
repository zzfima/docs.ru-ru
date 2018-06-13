---
title: Метод IMetaDataEmit::DefineSecurityAttributeSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60cb1640d374ce71d1d2fb51ba536b53ddd39b92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443533"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a>Метод IMetaDataEmit::DefineSecurityAttributeSet
Создает набор разрешений безопасности, чтобы присоединить объект, который ссылается указанный токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tkObj`  
 [in] Маркер, с которым необходимо связать сведения о безопасности.  
  
 `rSecAttrs`  
 [in] Массив `COR_SECATTR` структуры.  
  
 `cSecAttrs`  
 [in] Число элементов в `rSecAttrs`.  
  
 `pulErrorAttr`  
 [out] При сбое метода, указывает индекс в `rSecAttrs` элемента, который вызвал проблему.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
