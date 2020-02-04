---
title: Интерфейс ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790540"
---
# <a name="icorpublishprocess-interface"></a>Интерфейс ICorPublishProcess
Предоставляет методы, которые обращаются к сведениям, отображаемым в процессе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumAppDomains](icorpublishprocess-enumappdomains-method.md)|Возвращает экземпляр [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , содержащий домены приложений в процессе, на который ссылается эта `ICorPublishProcess`.|  
|[Метод GetDisplayName](icorpublishprocess-getdisplayname-method.md)|Возвращает полный путь к исполняемому файлу для процесса, на который ссылается эта `ICorPublishProcess`.|  
|[Метод GetProcessID](icorpublishprocess-getprocessid-method.md)|Возвращает идентификатор операционной системы для процесса, на который ссылается эта `ICorPublishProcess`.|  
|[Метод IsManaged](icorpublishprocess-ismanaged-method.md)|Возвращает значение, указывающее, называется ли процесс, на который ссылается эта `ICorPublishProcess`, выполнением управляемого кода.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)
