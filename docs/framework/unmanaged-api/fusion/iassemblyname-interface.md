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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134313"
---
# <a name="iassemblyname-interface"></a>Интерфейс IAssemblyName
Предоставляет методы для описания и работы с уникальным удостоверением сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](iassemblyname-clone-method.md)|Создает неполную копию этого объекта `IAssemblyName`.|  
|[Метод Finalize](iassemblyname-finalize-method.md)|Позволяет этому объекту `IAssemblyName` освобождать ресурсы и выполнять другие операции очистки перед вызовом деструктора.|  
|[Метод GetDisplayName](iassemblyname-getdisplayname-method.md)|Возвращает удобное для восприятия имя сборки, на которую ссылается этот объект `IAssemblyName`.|  
|[Метод GetName](iassemblyname-getname-method.md)|Возвращает простое незашифрованное имя сборки, на которую ссылается данный объект `IAssemblyName`.|  
|[Метод GetProperty](iassemblyname-getproperty-method.md)|Возвращает указатель на свойство, на которое ссылается заданный `PropertyId`.|  
|[Метод GetVersion](iassemblyname-getversion-method.md)|Возвращает сведения о версии для сборки, на которую ссылается данный объект `IAssemblyName`.|  
|[Метод IsEqual](iassemblyname-isequal-method.md)|Определяет, равен ли указанный объект `IAssemblyName` этому `IAssemblyName`на основе указанных флагов сравнения.|  
|[Метод SetProperty](iassemblyname-setproperty-method.md)|Задает значение свойства, на которое ссылается заданная `PropertyId`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IAssemblyEnum](iassemblyenum-interface.md)
