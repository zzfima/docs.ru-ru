---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 7531cf27aec0ea9a71ee7b1906e8f7cee151695f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485958"
---
# <a name="servicetimeoutsbehavior"></a>ServiceTimeoutsBehavior
ServiceTimeoutsBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceTimeoutsBehavior не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceTimeoutsBehavior имеет следующее свойство.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Период времени, в течение которого транзакция должна быть завершена.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
