---
title: "Разрешение вопросов. Отладка служб Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a>Разрешение вопросов. Отладка служб Windows
При отладке приложения службы Windows, службы и **Windows Service Manager** взаимодействия. **Service Manager** запускает службу путем вызова <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, а затем — 30 секунд для ожидания <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метод для возврата. Если метод не возвращает в течение этого времени, диспетчер отображает ошибку, что служба не запущена.  
  
 При отладке <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, как описано в [как: отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), необходимо иметь в виду этого 30-секундного периода. Если установить точку останова в <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода и не пройти ее за 30 секунд, служба не запускается диспетчер.  
  
## <a name="see-also"></a>См. также  
 [Как: отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
