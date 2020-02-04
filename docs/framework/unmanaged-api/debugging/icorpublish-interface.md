---
title: Интерфейс ICorPublish
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790728"
---
# <a name="icorpublish-interface"></a>Интерфейс ICorPublish
Служит общим интерфейсом для публикации сведений о процессах и сведениях о доменах приложений в этих процессах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumProcesses](icorpublish-enumprocesses-method.md)|Возвращает экземпляр [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , содержащий управляемые процессы, запущенные на этом компьютере.|  
|[Метод GetProcess](icorpublish-getprocess-method.md)|Возвращает экземпляр [ICorPublishProcess](icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)
