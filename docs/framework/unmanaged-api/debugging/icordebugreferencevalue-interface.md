---
title: ICorDebugReferenceValue интерфейс1
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
ms.openlocfilehash: b6cdfa9f3717e4025ff6f4fe6da3c1457cdebf7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422335"
---
# <a name="icordebugreferencevalue-interface1"></a>ICorDebugReferenceValue интерфейс1
Предоставляет методы, управляющие значением, которое является ссылкой на объект. (То есть этот интерфейс предоставляет методы, управляющие указателя). Этот интерфейс реализует «ICorDebugValue».  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Dereference](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Возвращает объект, на который имеется ссылка.|  
|[Метод DereferenceStrong](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Не реализовано. Не вызывайте этот метод.|  
|[Метод GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Получает текущий адрес памяти объекта, на который указывает ссылка.|  
|[Метод IsNull](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Возвращает значение, указывающее, является ли это `ICorDebugReferenceValue` имеет значение null, в этом случае `ICorDebugReferenceValue` не указывает на объект.|  
|[Метод SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Задает текущий адрес памяти. То есть этот метод задает это `ICorDebugReferenceValue` для указания на объект.|  
  
## <a name="remarks"></a>Примечания  
 Общеязыковая среда выполнения (CLR) может выполнить сборку мусора для объектов после возобновления процесса отладки. Сборка мусора может перемещаться объектов в памяти. `ICorDebugReferenceValue` Будет либо взаимодействовать со сбором мусора, чтобы его данные обновляются после сборки мусора, или он будет неявно объявлен недействительным перед сборкой мусора.  
  
 `ICorDebugReferenceValue` Объект может быть объявлен недействительным неявным образом после возобновлена отлаживаемого процесса. Производный» ICorDebugHandleValue» становится недействительным, пока не будет явно выпуска или предоставляется.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
    
    
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
