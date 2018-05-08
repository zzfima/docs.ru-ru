---
title: Управление автозапуском узла службы WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: fe936ee3ff42b586c733de597de808b86f3e2575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Управление автозапуском узла службы WCF
Можно управлять возможностью автозапуска узла службы Windows Communication Foundation (WCF) (WcfSvcHost.exe) для [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] проекта библиотеки службы при отладке другого проекта того же решения Visual Studio содержит несколько проектов .  
  
 Чтобы сделать это, щелкните правой кнопкой мыши [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] проект службы в **обозревателе решений**, выберите **свойства**и нажмите кнопку **параметры WCF** вкладки. **Запуск узла службы WCF при отладке другого проекта того же решения** флажок установлен по умолчанию. Можно снять этот флажок, чтобы узел службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] не запускался для заданного проекта при отладке другого проекта в одном решении.  
  
 Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.  
  
 Эта возможность доступна в следующих проектах.  
  
-   Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Проект библиотеки службы последовательного рабочего процесса.  
  
-   Проект библиотеки рабочего процесса конечного автомата.  
  
-   Проект библиотеки служб синдикации.  
  
## <a name="see-also"></a>См. также  
 [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
