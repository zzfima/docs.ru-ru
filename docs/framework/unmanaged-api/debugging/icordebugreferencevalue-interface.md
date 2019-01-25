---
title: Интерфейс1 ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dbe5388d7c18202f4b89269141d33463edb07a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544277"
---
# <a name="icordebugreferencevalue-interface1"></a>Интерфейс1 ICorDebugReferenceValue
Предоставляет методы, управляющие значением, которое является ссылкой на объект. (То есть этот интерфейс предоставляет методы, управляющие указатель). Этот интерфейс реализует «ICorDebugValue».  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Dereference](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Получает объект, на который приведена ссылка.|  
|[Метод DereferenceStrong](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Не реализовано. Этот метод не вызывается.|  
|[Метод GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Получает текущий адрес памяти объекта, на который указывает ссылка.|  
|[Метод IsNull](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Получает значение, указывающее, является ли это `ICorDebugReferenceValue` имеет значение null, в этом случае `ICorDebugReferenceValue` не указывает на объект.|  
|[Метод SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Задает текущий адрес памяти. То есть, этот метод устанавливает это `ICorDebugReferenceValue` для указания на объект.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR (CLR) может сделать сбор мусора для объектов, когда продолжает выполнение отлаживаемого процесса. Сборка мусора может перемещать объекты в памяти. `ICorDebugReferenceValue` Будет либо сотрудничать со сборкой мусора, чтобы его сведения обновляются после сборки мусора, или он будет недействительным неявно перед сборкой мусора.  
  
 `ICorDebugReferenceValue` Объект может быть неявно недействительными после возобновлена отлаживаемого процесса. Производный «ICorDebugHandleValue» не является недействительным, пока не будет явно выпуска или предоставляются.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также


- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
