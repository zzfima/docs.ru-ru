---
title: Интерфейс IMetaDataDispenser
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: b7ce76c22e7188117bddd9e4f328e323f6742685
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436228"
---
# <a name="imetadatadispenser-interface"></a>Интерфейс IMetaDataDispenser
Provides methods to create a new metadata scope, or open an existing one.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DefineScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|Creates a new area in memory where you can create new metadata.|  
|[Метод OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|Opens an existing, on-disk file and maps its metadata into memory.|  
|[Метод OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|Opens an area of memory that contains existing metadata. That is, this method opens a specified area of memory in which the existing data is treated as metadata.|  
  
## <a name="requirements"></a>Требования  
 **Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
