---
title: 'Устранение неполадок: Отладка служб Windows'
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
ms.openlocfilehash: cbedb0051cbb08c2875e145a2bad35ae4d02a74e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053511"
---
# <a name="troubleshooting-debugging-windows-services"></a>Устранение неполадок: Отладка служб Windows
При отладке приложения-службы Windows происходит взаимодействие между службой и диспетчером **Windows Service Manager**. **Service Manager** запускает службу, вызывая метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, после чего 30 секунд ожидает возврат метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Если метод не возвращается за это время, диспетчер отображает ошибку о невозможности запустить службу.  
  
 При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, как описано в статье [Практическое руководство. Отладка приложений-служб Windows](how-to-debug-windows-service-applications.md), необходимо помнить об этом 30-секундном периоде. Если в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> установить точку останова и не пройти ее за 30 секунд, диспетчер не запустит службу.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Отладка приложений служб Windows](how-to-debug-windows-service-applications.md)
- [Знакомство с приложениями служб Windows](introduction-to-windows-service-applications.md)
