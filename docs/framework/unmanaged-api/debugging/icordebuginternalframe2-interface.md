---
title: Интерфейс ICorDebugInternalFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2377773b471b387376f0284522ebe29d6b003ae3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910111"
---
# <a name="icordebuginternalframe2-interface"></a>Интерфейс ICorDebugInternalFrame2
Предоставляет сведения о внутренних кадрах, включая адрес стека и расположение по отношению к объектам ICorDebugFrame.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetFrameAddress](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|Возвращает адрес стека внутреннего кадра.|  
|[Метод IsCloserToLeaf](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|Проверяет, находится `this` ли внутренний кадр ближе к конечному объекту, чем указанный объект ICorDebugFrame.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс расширяет интерфейс ICorDebugInternalFrame.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
