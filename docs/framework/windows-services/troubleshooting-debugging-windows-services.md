---
title: Разрешение вопросов. Отладка служб Windows
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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-debugging-windows-services"></a>Разрешение вопросов. Отладка служб Windows
При отладке приложения службы Windows, службы и **Windows Service Manager** взаимодействия. **Service Manager** запускает службу путем вызова <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, а затем — 30 секунд для ожидания <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метод для возврата. Если метод не возвращает в течение этого времени, диспетчер отображает ошибку, что служба не запущена.  
  
 При отладке <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, как описано в [как: отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), необходимо иметь в виду этого 30-секундного периода. Если установить точку останова в <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода и не пройти ее за 30 секунд, служба не запускается диспетчер.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
