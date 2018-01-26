---
title: "Интерфейс IAssemblyName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName
helpviewer_keywords: IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 902ad9f67d06306e79666f0e10d85bdb9c65c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyname-interface"></a>Интерфейс IAssemblyName
Предоставляет методы для описания и работы с уникальный идентификатор сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|Создает неполную копию `IAssemblyName` объекта.|  
|[Метод Finalize](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|Это позволяет `IAssemblyName` объект освободить ресурсы и выполнить другие операции очистки, перед его деструктора.|  
|[Метод GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|Возвращает понятное имя сборки, упоминаемой в этом `IAssemblyName` объекта.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|Получает простое, нешифрованное имя сборки, упоминаемой в этом `IAssemblyName` объекта.|  
|[Метод GetProperty](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|Получает указатель ссылается заданный дескриптор свойства `PropertyId`.|  
|[Метод GetVersion](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|Возвращает сведения о версии для сборки, упоминаемой в этом `IAssemblyName` объекта.|  
|[Метод IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|Определяет, является ли заданное `IAssemblyName` объект равен этому `IAssemblyName`, основываясь на флаги сравнения указанного.|  
|[Метод SetProperty](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|Задает значение свойства, который ссылается заданный дескриптор `PropertyId`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Интерфейс IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
