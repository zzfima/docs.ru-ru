---
title: О пространстве имен System.Net.PeerToPeer.Collaboration
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
ms.openlocfilehash: f0c9ecaacc1d875aac8eed61a85ca7579f5cb8a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "64649525"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a>О пространстве имен System.Net.PeerToPeer.Collaboration
Пространство имен <xref:System.Net.PeerToPeer.Collaboration> предоставляет классы и API, которые применяются для реализации функций однорангового взаимодействия с использованием инфраструктуры одноранговой совместной работы.  
  
## <a name="classes"></a>Классы  
 Ниже перечислены основные классы, используемые для реализации возможностей одноранговой совместной работы:  
  
- Класс <xref:System.Net.PeerToPeer.Collaboration.ContactManager> используется для хранения одноранговых контактов.  
  
- Класс <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> реализует возможности совместной работы, например игры, клиенты чата или решение для проведения конференций.  
  
- Одноранговые узлы, которые будут участвовать в совместной работе.  Такие одноранговые узлы могут быть представлены как объекты <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> или <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>.  
  
- Статический класс <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> определяет доступные приложения и одноранговые узлы, которые участвуют в них.  
  
 Методы <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> используются для приглашения одноранговых узлов в сеанс совместной работы.  Вызывающий одноранговый узел может подписаться на события другого однорангового узла, сигнализирующие об обновлениях приложения, объекта или сведений о присутствии в рамках сеанса совместной работы. Классы сведения о присутствии указывают, доступен ли объект <xref:System.Net.PeerToPeer.Collaboration.Peer> для совместной работы. Класс <xref:System.Net.PeerToPeer.Collaboration.PeerScope> указывает уровень разрешений на участие для однорангового узла: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (глобальная сеть), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe> (подсеть) или <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.  
  
 Сеанс совместной работы состоит из четырех шагов:  
  
- Обнаружение. Обнаружение или публикация приложений, одноранговых узлов и сведений о присутствии.  Например, поиск других пользователей локальной подсети, у которых установлены те же игры.  
  
- Приглашение. Отправка и принятие защищенных приглашений, посредством которых удаленные одноранговые узлы могут начинать сеансы <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> или присоединяться к ним.  
  
- Управление контактами. Добавление обнаруженных одноранговых узлов в качестве контактов в <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
- Взаимодействие. Организация многостороннего взаимодействия с использованием API <xref:System.Net>, API <xref:System.Net.PeerToPeer> или классов одноранговых каналов платформы Windows Communication Foundation.  
  
 Например, ведущий одноранговый узел запускает сеанс совместной работы и использует метод <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A>, чтобы добавить удаленный узел и один из своих локальных одноранговых узлов в собственный диспетчер контактов.  Эти три пользователя будут участвовать в собственном закрытом сеансе совместной работы.  
  
 Распространенные одноранговые приложения: конференции, совместная работа с заметками или досками, приложения чата без сервера, интерактивная реклама и интернет-игры.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.PeerToPeer.Collaboration>
