---
title: Интерфейс IAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d89a531ad09e6865bd9c7dad00c1d8c1840fab8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662170"
---
# <a name="iassemblycacheitem-interface"></a>Интерфейс IAssemblyCacheItem
Представляет одну сборку в глобальный кэш сборок.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод AbortItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|Позволяет сборку в глобальный кэш сборок для выполнения операции очистки, перед выпуском.|  
|[Метод Commit](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|Фиксирует ссылки на сборку, кэшированных в памяти.|  
|[Метод CreateStream](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|Создает поток с указанным именем и формат.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
- [Интерфейс IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
