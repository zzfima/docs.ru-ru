---
title: "Метод IMetaDataEmit::SetClassLayout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e0c02e615bf77a2cc9136b50efd7395585959141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetclasslayout-method"></a>Метод IMetaDataEmit::SetClassLayout
Завершает макета полей для класса, который был определен во время предыдущего вызова для [метод DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] `mdTypeDef` Маркер, указывающий класс располагаться.  
  
 `dwPackSize`  
 [in] Размер упаковки: 1, 2, 4, 8 или 16 байт. Размер пакета — число байтов между смежными полями.  
  
 `rFieldOffsets`  
 [in] Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) структуры, каждый из которых задает поля класса и смещение в пределах класса. Массива с `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Размер в байтах класса.  
  
## <a name="remarks"></a>Примечания  
 Класс был изначально определен путем вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) метод и задавая один из трех структур поля класса: автоматически, последовательные или явно. Как правило следует использовать автоматический макет и позволить среде выполнения выбрать лучший способ расположения полей.  
  
 Тем не менее может потребоваться поля, располагались в порядке их использования неуправляемым кодом. В этом случае выберите явную или последовательный макет и вызов `SetClassLayout` для завершения макета полей:  
  
-   Последовательное размещение: укажите размер упаковки. Поле выравниваются в соответствии с его фактическим размером или упаковочный размер, что приводит меньшего размера смещение поля. Задать `rFieldOffsets` и `ulClassSize` до нуля.  
  
-   Явно заданный макет: задайте смещение каждого поля, или установите размер класса и упаковочный размер.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
