---
title: "PNRP в разработке приложений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# PNRP в разработке приложений
В Windows Vista, приложения сети могут получить доступ к функциям публикации и разрешения имени через протокол PNRP упрощенный программный интерфейс \(API\).  
  
## Реализация протокола PNRP  
 С упрощенным API PNRP, не определены, что регистрируют облака явно имя и адрес. компонент автоматически определяет соответствующие облака PNRP для соединения и адреса публиковать в облаке.  
  
 Для строго упрощенного разрешения имен протокола PNRP в Windows Vista, имена PNRP теперь интегрированы в функцию Windows sockets getaddrinfo\(\).  Для использования протокола PNRP разрешить имя адреса IP версии 6 приложения могут использовать функцию getaddrinfo\(\), чтобы дать полное имя домена \(полное доменное имя\) name.prnp.  net, в котором имя, разрешенным имя однорангового узла.  Pnrp.  net домен является зарезервированным домен, в Windows Vista для разрешения имен протокола PNRP.  
  
 PeerToPeer передачи сообщений между приложениями по\-прежнему изменяется основными архитектурами и как PeerChannel WCF [большие данные и потоковая передача](http://go.microsoft.com/fwlink/?LinkID=179652).  
  
## См. также  
 <xref:System.Net.PeerToPeer>