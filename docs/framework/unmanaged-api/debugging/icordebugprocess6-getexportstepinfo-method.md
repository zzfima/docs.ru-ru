---
title: Метод ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18af0dde2d1acc65003558a04789de027bb9209f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967398"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>Метод ICorDebugProcess6::GetExportStepInfo
Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a>Параметры  
 pszExportName  
 [входной] Имя функции экспорта во время выполнения, записываемой в таблице экспорта PE.  
  
 invokeKind  
 заполняет Указатель на член перечисления [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) , описывающий, как экспортируемая функция будет вызывать управляемый код.  
  
 invokePurpose  
 заполняет Указатель на член перечисления [кордебугкодеинвокепурпосе](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) , описывающий, почему экспортируемая функция будет вызывать управляемый код.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод может возвращать значения, перечисленные в следующей таблице.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`S_OK`|Успешный вызов метода.|  
|`E_POINTER`|`pInvokeKind`или `pInvokePurpose` имеет **значение NULL**.|  
|Другие ошибочные значения `HRESULT`.|По мере необходимости.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
