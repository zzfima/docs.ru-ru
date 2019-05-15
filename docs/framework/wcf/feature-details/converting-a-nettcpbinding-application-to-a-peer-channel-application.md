---
title: Преобразование приложения NetTcpBinding в приложение одноранговых каналов
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: b89afbe59b73288ba357fa55ec5d55c1fb18352b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582784"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Преобразование приложения NetTcpBinding в приложение одноранговых каналов
Привязки, описывающие параметры подключения, позволяют создавать подключения между клиентами с использованием [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Преобразование приложения .NET Framework для использования подключений peer-to-peer требуется привязка, поддерживающая эту технологию при установлении соединений клиента. Одноранговый канал предоставляет привязку, называемую <xref:System.ServiceModel.NetPeerTcpBinding>, которую можно использовать аналогично привязке <xref:System.ServiceModel.NetTcpBinding>. Основное отличие в том, как задается служба распознавателя и определяются параметры безопасности.  
  
 Если приложение использует распознаватель и параметры безопасности по умолчанию, преобразование обычного клиентско-серверного приложения для использования однорангового канала предполагает изменение имени привязки с "NetTcpBinding" на "NetPeerTcpBinding" в файле конфигурации приложения, при этом не требуется изменять базу кода приложения.  
  
## <a name="see-also"></a>См. также

- [Создание приложения одноранговых каналов](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
