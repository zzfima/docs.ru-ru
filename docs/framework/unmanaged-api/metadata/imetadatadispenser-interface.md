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
Предоставляет методы для создания новой области метаданных или открытия существующей.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DefineScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|Создает новую область в памяти, в которой можно создавать новые метаданные.|  
|[Метод OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|Открывает существующий файл на диске и сопоставляет его метаданные с памятью.|  
|[Метод OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|Открывает область памяти, которая содержит существующие метаданные. Это значит, что этот метод открывает указанную область памяти, в которой существующие данные обрабатываются как метаданные.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
