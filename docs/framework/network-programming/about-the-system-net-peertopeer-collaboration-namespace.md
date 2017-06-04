---
title: "О пространстве имен System.Net.PeerToPeer.Collaboration | Microsoft Docs"
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
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# О пространстве имен System.Net.PeerToPeer.Collaboration
Пространство имен <xref:System.Net.PeerToPeer.Collaboration> предоставляет классы и api\-интерфейсы, используемые для реализации действия совместной работы в одноранговой сети с использованием одноранговой инфраструктуре совместной работы.  
  
## Классы  
 Основные классы, используемые в реализации одноранговой действии взаимодействия:  
  
-   <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, который можно использовать для хранения контактов одноранговых узлов.  
  
-   <xref:System.Net.PeerToPeer.Collaboration.PeerApplication>, в котором для совместной работы, например игры, клиент диалога или решения запускать конференций.  
  
-   Одноранговые, которые будут работать совместно в действии.  Эти узлы могут быть представлены как <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> или объекты <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>.  
  
-   Статический класс является <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>, который определяет, доступны и приложения, одноранговые узлы участвуют в них.  
  
 Методы <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> используются для пригласить одноранговые к сеансу совместной работы.  Вызывающий одноранговый узел, может подписываться на другом узле для событий, сигнал обновляет к приложению объект или сведения о присутствии приниманным с сеансом взаимодействия.  Классы присутствия определяют, является ли <xref:System.Net.PeerToPeer.Collaboration.Peer> доступно для взаимодействия и класс <xref:System.Net.PeerToPeer.Collaboration.PeerScope> используется для определения количества разрешено для участия в одноранговой сети. <xref:System.Net.PeerToPeer.Collaboration.PeerScope> \(global\), <xref:System.Net.PeerToPeer.Collaboration.PeerScope>\(подсеть\) или <xref:System.Net.PeerToPeer.Collaboration.PeerScope>.  
  
 Сеанс взаимодействия состоит из 4 шагов:  
  
-   Представление.  Откройте или публиковать приложение одноранговых и сведения о присутствии.  Например, найти другие лица в локальной подсети, имеющие одинаковые игры быть задано.  
  
-   Приглашение.  Отправляйте и принимайте безопасные запросы для удаленных одноранговых запускать сеансы и соединения <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>.  
  
-   Управление контактами.  Добавление открыло одноранговые как контакт в <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
-   Сообщение.  При установке сообщение, использовать API <xref:System.Net> API <xref:System.Net.PeerToPeer> или одноранговый канал Windows Communication Foundation классифицирует для многопользовательские сообщений.  
  
 Например, одноранговый узел узла запускает сеанс взаимодействия и используется метод <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> для добавления удаленный одноранговый узел и одного из своих локальных узлов к диспетчеру контактов одноранговых узла.  3 Пользователей, после чего будут участвовать в своем собственном частном сеансе совместной работы.  
  
 Типичные приложения P2P: конференц\-связи для сотруднические заметка\- создания или whiteboarding без сервера приложения диалога, интерактивные объявления и подключенные сеансы разыгрыша.  
  
## См. также  
 <xref:System.Net.PeerToPeer.Collaboration>