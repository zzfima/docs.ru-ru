---
title: Интерфейс ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 472ea0b3d54c025cdd69957765ad2663c7288b15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783569"
---
# <a name="icordebugdatatarget2-interface"></a>Интерфейс ICorDebugDataTarget2
Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateVirtualUnwinder](icordebugdatatarget2-createvirtualunwinder-method.md)|Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).|  
|[Метод EnumerateThreadIDs](icordebugdatatarget2-enumeratethreadids-method.md)|Возвращает список идентификаторов активных потоков.|  
|[Метод GetImageFromPointer](icordebugdatatarget2-getimagefrompointer-method.md)|Возвращает базовый адрес и размер модуля из адреса в этом модуле.|  
|[Метод GetImageLocation](icordebugdatatarget2-getimagelocation-method.md)|Возвращает путь для модуля из базового адреса модуля.|  
|[Метод GetSymbolProviderForImage](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Возвращает поставщика символов для модуля из базового адреса модуля.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
