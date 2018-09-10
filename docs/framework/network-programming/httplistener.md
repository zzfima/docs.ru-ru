---
title: Класс HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 68c69de839ccbd51de9f0bfa74be018f877f7731
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085913"
---
# <a name="httplistener"></a>Класс HttpListener
Класс <xref:System.Net.HttpListener> предоставляет программно управляемый прослушиватель протокола HTTP. Прослушиватель активен в течение времени существования <xref:System.Net.HttpListener> объекта и выполняется в приложении.  
  
## <a name="httpsys"></a>HTTP.SYS  
 Класс <xref:System.Net.HttpListener> построен на базе HTTP.sys, который является прослушивателем режима ядра, обрабатывающим весь трафик HTTP для Windows. HTTP.sys обеспечивает управление соединениями, регулирование полосы пропускания и ведение журналов веб-сервера. Используйте средство `HttpCfg.exe` для добавления SSL-сертификатов. Дополнительные сведения см. в документации к средству [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) в документации к [серверу](https://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [HTTP-сервер](https://go.microsoft.com/fwlink/?LinkID=178285)  
 [Усовершенствования безопасности в Internet Information](https://go.microsoft.com/fwlink/?LinkID=178286)  
 [Образец ведущего приложения ASPX HttpListener](https://go.microsoft.com/fwlink/?LinkID=179560)  
 [Пример технологии HttpListener](https://go.microsoft.com/fwlink/?LinkID=179558)  
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)
