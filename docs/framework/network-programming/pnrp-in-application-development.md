---
title: PNRP в разработке приложений
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0f86b2569b9d4864586a0a7daea0ae5d3b901fd4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47205269"
---
# <a name="pnrp-in-application-development"></a>PNRP в разработке приложений
В ОС Windows Vista сетевые приложения могут получать доступ к функциям публикации и разрешения имен через упрощенный программный интерфейс (API) PNRP.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Реализация протокола PNRP  
 С помощью упрощенного API PNRP не задаются явно облака для регистрации имен и адресов. Компонент PNRP автоматически определяет соответствующие облака, к которым требуется присоединиться, и адреса для публикации в них.  
  
 В оптимально упрощенном разрешении имен PNRP в системе Windows Vista PNRP-имена теперь интегрированы в функцию Windows Sockets getaddrinfo(). При использовании PNRP для преобразования имени в IPv6-адрес приложения могут пользоваться функцией getaddrinfo() для преобразования полного доменного имени (FQDN) name.prnp.net, в котором name — это имя однорангового узла, которое преобразуется. Домен pnrp.net — это зарезервированный домен в Windows Vista для разрешения имен PNRP.  
  
 Передача сообщений между одноранговыми приложениями по-прежнему осуществляется с применением базовых архитектур, таких как PeerChannel и [Большие наборы данных и потоковая передача](https://go.microsoft.com/fwlink/?LinkID=179652) WCF.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.PeerToPeer>
