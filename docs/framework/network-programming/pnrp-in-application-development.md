---
title: PNRP в разработке приложений
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: 4cd0d739e58cd252213e8d5c16d29cc612338df6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178143"
---
# <a name="pnrp-in-application-development"></a>PNRP в разработке приложений
В ОС Windows Vista сетевые приложения могут получать доступ к функциям публикации и разрешения имен через упрощенный программный интерфейс (API) PNRP.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Реализация протокола PNRP  
 С помощью упрощенного API PNRP не задаются явно облака для регистрации имен и адресов. Компонент PNRP автоматически определяет соответствующие облака, к которым требуется присоединиться, и адреса для публикации в них.  
  
 В оптимально упрощенном разрешении имен PNRP в системе Windows Vista PNRP-имена теперь интегрированы в функцию Windows Sockets getaddrinfo(). При использовании PNRP для преобразования имени в IPv6-адрес приложения могут пользоваться функцией getaddrinfo() для преобразования полного доменного имени (FQDN) name.prnp.net, в котором name — это имя однорангового узла, которое преобразуется. Домен pnrp.net — это зарезервированный домен в Windows Vista для разрешения имен PNRP.  
  
 Передача сообщений между одноранговыми приложениями по-прежнему осуществляется с применением базовых архитектур, таких как PeerChannel и [Большие наборы данных и потоковая передача](https://go.microsoft.com/fwlink/?LinkID=179652) WCF.  
  
## <a name="see-also"></a>См. также

- <xref:System.Net.PeerToPeer>
