---
title: Интерфейс IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440163"
---
# <a name="imetadatafilter-interface"></a>Интерфейс IMetaDataFilter
Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод IsTokenMarked](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Возвращает значение, указывающее, был ли обработан заданный маркер метаданных.|  
|[Метод MarkToken](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Задает значение, указывающее, что указанный токен метаданных был обработан.|  
|[Метод UnmarkAll](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Удаляет метки обработки из всех токенов в текущей области метаданных.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
