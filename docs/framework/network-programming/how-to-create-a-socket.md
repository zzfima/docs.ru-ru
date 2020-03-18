---
title: Практическое руководство. Создание сокета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: e71e7e235048361580c65bdb551919fe3038130b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180823"
---
# <a name="how-to-create-a-socket"></a>Практическое руководство. Создание сокета
Перед использованием сокета для связи с удаленными устройствами необходимо инициализировать сокет, указав протокол и сведения о сетевом адресе. Конструктор класса <xref:System.Net.Sockets.Socket> имеет параметры, которые определяют семейство адресов, тип сокета и тип протокола, которые сокет использует для подключения.  
  
## <a name="example"></a>Пример  
 В следующем примере создается объект Socket, который может использоваться для обмена данными в сетях на основе TCP/IP (например, в Интернете).  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 Чтобы использовать UDP вместо TCP, измените тип протокола, как показано в следующем примере:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 В перечислении <xref:System.Net.Sockets.AddressFamily> указаны стандартные семейства адресов, которые используются классом **Socket** для разрешения сетевых адресов (например, элемент **AddressFamily.InterNetwork** задает семейство адресов протокола IP версии 4).  
  
 В перечислении <xref:System.Net.Sockets.SocketType> указан тип сокета (например, элемент **SocketType.Stream** указывает стандартный сокет для отправки и получения данных с помощью управления потоком).  
  
 В перечислении <xref:System.Net.Sockets.ProtocolType> указан сетевой протокол, который используется для связи с объектом **Socket** (например, **ProtocolType.Tcp** означает, что сокет использует TCP; **ProtocolType.Udp** означает, что сокет использует UDP).  
  
 После создания объекта **Socket** он может создать подключение к удаленной конечной точке или принимать подключения от удаленных устройств.  
  
## <a name="see-also"></a>См. также раздел

- [Использование сокетов клиента](using-client-sockets.md)
- [Прослушивание с помощью сокетов](listening-with-sockets.md)
