---
title: "Класс HttpListener"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b4b8c1e916aa9382d156a197fa15c2e72e900a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="httplistener"></a>Класс HttpListener
Класс <xref:System.Net.HttpListener> предоставляет программно управляемый прослушиватель протокола HTTP. Прослушиватель активен в течение времени существования <xref:System.Net.HttpListener> объекта и выполняется в приложении.  
  
## <a name="httpsys"></a>HTTP.SYS  
 Класс <xref:System.Net.HttpListener> построен на базе HTTP.sys, который является прослушивателем режима ядра, обрабатывающим весь трафик HTTP для Windows. HTTP.sys обеспечивает управление соединениями, регулирование полосы пропускания и ведение журналов веб-сервера. Используйте средство `HttpCfg.exe` для добавления SSL-сертификатов. Дополнительные сведения см. в документации к средству [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) в документации к [серверу](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [HTTP-сервера](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [Усовершенствования безопасности в Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [Образец ведущего приложения ASPX HttpListener](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [Пример технологии HttpListener](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)
