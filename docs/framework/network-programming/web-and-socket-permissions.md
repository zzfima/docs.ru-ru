---
title: Веб-разрешения и разрешения сокетов
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4353f029d2e82460ab413bc8ccc248577a505504
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="web-and-socket-permissions"></a>Веб-разрешения и разрешения сокетов
Безопасность приложений, использующих пространство имен <xref:System.Net>, в Интернете обеспечивается классами <xref:System.Net.WebPermission> и <xref:System.Net.SocketPermission>. Класс **WebPermission** определяет право приложения на запрос данных из универсального кода ресурса (URI) или предоставления кода URI в Интернете. Класс **SocketPermission** определяет право приложения на использование <xref:System.Net.Sockets.Socket> для приема данных через локальный порт или на связь с удаленными устройствами с помощью транспортного протокола по другому адресу в соответствии с узлом, номером порта и транспортным протоколом сокета.  
  
 Выбор используемого класса разрешений зависит от типа приложения. Приложения, применяющие класс <xref:System.Net.WebRequest> и его потомки, должны использовать класс **WebPermission** для управления разрешениями. Приложения, применяющие доступ на уровне сокета, должны использовать класс **SocketPermission** для управления разрешениями.  
  
 Классы **WebPermission** и **SocketPermission** определяют два разрешения: на прием и подключение. Разрешение на прием позволяет приложению отвечать на входящие запросы подключения от другой стороны. Разрешение на подключение позволяет приложению инициировать соединение с другой стороной.  
  
 Для экземпляров **SocketPermission** разрешение на прием означает, что приложение может принимать входящие подключения по локальному адресу транспорта. Разрешение на подключение означает, что приложение может подключаться к определенному удаленному (или локальному) адресу транспорта.  
  
 Для экземпляров **WebPermission** разрешение на прием означает, что приложение может экспортировать код URI, контролируемый экземпляром **WebPermission**, во внешнюю сеть. Разрешение на подключение означает, что приложение может получать доступ к этому коду URI (удаленному или локальному).  
  
## <a name="see-also"></a>См. также  
 [Безопасность](../../../docs/standard/security/index.md)  
 [Безопасность в сетевом программировании](../../../docs/framework/network-programming/security-in-network-programming.md)
