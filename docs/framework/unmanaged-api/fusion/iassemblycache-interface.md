---
title: Интерфейс IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157cc9f5f520f376c0c055ab49b116bc7961f421
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641074"
---
# <a name="iassemblycache-interface"></a>Интерфейс IAssemblyCache
Представляет глобальный кэш сборок для использования технологией fusion.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод CreateAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|Получает ссылку на новый [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).|  
|[Метод CreateAssemblyScavenger](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Зарезервировано для внутреннего использования технологией fusion.|  
|[Метод InstallAssembly](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|Устанавливает указанную сборку в глобальный кэш сборок.|  
|[Метод QueryAssemblyInfo](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|Получает запрашиваемые данные об указанной сборки.|  
|[Метод UninstallAssembly](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|Удаляет указанную сборку из глобального кэша сборок.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
