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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad77aba02c819749794534ca2ecd478661bc363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatafilter-interface"></a>Интерфейс IMetaDataFilter
Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод IsTokenMarked](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Возвращает значение, указывающее, была ли обработана указанным токеном метаданных.|  
|[Метод MarkToken](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Задает значение, указывающее, что указанный токен метаданных был обработан.|  
|[Метод UnmarkAll](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Удаляет знаки обработки изо всех маркеров в текущей области метаданных.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
