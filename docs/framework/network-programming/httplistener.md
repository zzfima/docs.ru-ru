---
title: "Класс HttpListener"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 44620273fc2497675a26a6905dfdc52db1aaab3f
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="httplistener"></a>Класс HttpListener
Класс <xref:System.Net.HttpListener> предоставляет программно управляемый прослушиватель протокола HTTP. Прослушиватель активен в течение времени существования <xref:System.Net.HttpListener> объекта и выполняется в приложении.  
  
## <a name="httpsys"></a>HTTP.SYS  
 Класс <xref:System.Net.HttpListener> построен на базе HTTP.sys, который является прослушивателем режима ядра, обрабатывающим весь трафик HTTP для Windows. HTTP.sys обеспечивает управление соединениями, регулирование полосы пропускания и ведение журналов веб-сервера. Используйте средство `HttpCfg.exe` для добавления SSL-сертификатов. Дополнительные сведения см. в документации к средству [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) в документации к [серверу](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 [HTTP-сервер](http://go.microsoft.com/fwlink/?LinkID=178285)   
 [Усовершенствования безопасности в Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286)   
 [Образец ведущего приложения ASPX HttpListener](http://go.microsoft.com/fwlink/?LinkID=179560)   
 [Пример технологии HttpListener](http://go.microsoft.com/fwlink/?LinkID=179558)   
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)

