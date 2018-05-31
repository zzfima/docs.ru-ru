---
title: 'Устранение неполадок: отладка служб Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
manager: douge
ms.openlocfilehash: 77a0c19c2da2d1886beaf396650fa024fc1243a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510141"
---
# <a name="troubleshooting-debugging-windows-services"></a>Устранение неполадок: отладка служб Windows
При отладке приложения-службы Windows происходит взаимодействие между службой и диспетчером **Windows Service Manager**. **Service Manager** запускает службу, вызывая метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, после чего 30 секунд ожидает возврат метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Если метод не возвращается за это время, диспетчер отображает ошибку о невозможности запустить службу.  
  
 При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, как описано в статье [Практическое руководство. Отладка приложений-служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), необходимо помнить об этом 30-секундном периоде. Если в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> установить точку останова и не пройти ее за 30 секунд, диспетчер не запустит службу.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
