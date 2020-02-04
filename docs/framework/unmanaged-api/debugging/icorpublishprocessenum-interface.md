---
title: Интерфейс ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790499"
---
# <a name="icorpublishprocessenum-interface"></a>Интерфейс ICorPublishProcessEnum
Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishProcess](icorpublishprocess-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](icorpublishprocessenum-next-method.md)|Возвращает указанное число экземпляров `ICorPublishProcess` из коллекции, начиная с текущей позиции.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorPublishProcessEnum` реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).  
  
 Экземпляр `ICorPublishProcessEnum` создается методом [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) . Обход коллекции объектов `ICorPublishProcess` основан на условиях фильтра, заданных во время создания `ICorPublishProcessEnum` экземпляра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)
