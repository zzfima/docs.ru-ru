---
title: 'Конечная точка: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: f1b2997a0f1e16c897fc319d1833313141f5c4bf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199600"
---
# <a name="endpoint-calls-faulted-per-second"></a>Конечная точка: количество сбоев вызовов в секунду
Имя счетчика: Calls Faulted Per Second.  
  
## <a name="description"></a>Описание  
 Количество вызовов, которые возвратили сбой данной конечной точке в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 В приложениях Windows Communication Foundation (WCF) методы службы передают сведения об ошибке обработки с помощью сообщения об ошибках SOAP. Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы. Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.  
  
## <a name="see-also"></a>См. также  
 [Указание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
