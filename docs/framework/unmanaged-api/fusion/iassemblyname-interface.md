---
title: Интерфейс IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796550"
---
# <a name="iassemblyname-interface"></a>Интерфейс IAssemblyName
Предоставляет методы для описания и работы с уникальным удостоверением сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](iassemblyname-clone-method.md)|Создает неполную копию этого `IAssemblyName` объекта.|  
|[Метод Finalize](iassemblyname-finalize-method.md)|Разрешает этому `IAssemblyName` объекту освобождать ресурсы и выполнять другие операции очистки перед вызовом деструктора.|  
|[Метод GetDisplayName](iassemblyname-getdisplayname-method.md)|Возвращает удобное для восприятия имя сборки, на которую ссылается `IAssemblyName` этот объект.|  
|[Метод GetName](iassemblyname-getname-method.md)|Возвращает простое незашифрованное имя сборки, на которую ссылается этот `IAssemblyName` объект.|  
|[Метод GetProperty](iassemblyname-getproperty-method.md)|Возвращает указатель на свойство, на которое ссылается указанный `PropertyId`объект.|  
|[Метод GetVersion](iassemblyname-getversion-method.md)|Возвращает сведения о версии для сборки, на которую ссылается `IAssemblyName` этот объект.|  
|[Метод IsEqual](iassemblyname-isequal-method.md)|Определяет, равен ли `IAssemblyName` указанный объект этому `IAssemblyName`объекту на основе указанных флагов сравнения.|  
|[Метод SetProperty](iassemblyname-setproperty-method.md)|Задает значение свойства, на которое ссылается указанный `PropertyId`объект.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IAssemblyEnum](iassemblyenum-interface.md)
