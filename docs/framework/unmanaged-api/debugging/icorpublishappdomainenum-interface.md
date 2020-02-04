---
title: Интерфейс ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790674"
---
# <a name="icorpublishappdomainenum-interface"></a>Интерфейс ICorPublishAppDomainEnum
Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , которые в данный момент существуют в процессе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](icorpublishappdomainenum-next-method.md)|Возвращает указанное число экземпляров `ICorPublishAppDomain` из коллекции, начиная с текущей позиции.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorPublishAppDomainEnum` реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)
