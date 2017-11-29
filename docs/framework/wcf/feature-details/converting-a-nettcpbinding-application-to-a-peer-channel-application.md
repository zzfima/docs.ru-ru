---
title: "Преобразование приложения NetTcpBinding в приложение одноранговых каналов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 532171dfeba965ae30dc92f31448cf38964fc695
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Преобразование приложения NetTcpBinding в приложение одноранговых каналов
Привязки, описывающие параметры подключения, позволяют создавать подключения между клиентами с использованием [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Преобразование приложения [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для использования одноранговых подключений требует привязки, которая поддерживает эту технологию при установке клиентских подключений. Одноранговый канал предоставляет привязку, называемую <xref:System.ServiceModel.NetPeerTcpBinding>, которую можно использовать аналогично привязке <xref:System.ServiceModel.NetTcpBinding>. Основное отличие в том, как задается служба распознавателя и определяются параметры безопасности.  
  
 Если приложение использует распознаватель и параметры безопасности по умолчанию, преобразование обычного клиентско-серверного приложения для использования однорангового канала предполагает изменение имени привязки с "NetTcpBinding" на "NetPeerTcpBinding" в файле конфигурации приложения, при этом не требуется изменять базу кода приложения.  
  
## <a name="see-also"></a>См. также  
 [Создание приложения одноранговых каналов](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
