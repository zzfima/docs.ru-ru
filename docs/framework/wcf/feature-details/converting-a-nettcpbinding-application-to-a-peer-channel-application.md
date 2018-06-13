---
title: Преобразование приложения NetTcpBinding в приложение одноранговых каналов
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 9cc73beeffc9daa9883832b3a6bedd0ff438095c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489002"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Преобразование приложения NetTcpBinding в приложение одноранговых каналов
Привязки, описывающие параметры подключения, позволяют создавать подключения между клиентами с использованием [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Преобразование приложения [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для использования одноранговых подключений требует привязки, которая поддерживает эту технологию при установке клиентских подключений. Одноранговый канал предоставляет привязку, называемую <xref:System.ServiceModel.NetPeerTcpBinding>, которую можно использовать аналогично привязке <xref:System.ServiceModel.NetTcpBinding>. Основное отличие в том, как задается служба распознавателя и определяются параметры безопасности.  
  
 Если приложение использует распознаватель и параметры безопасности по умолчанию, преобразование обычного клиентско-серверного приложения для использования однорангового канала предполагает изменение имени привязки с "NetTcpBinding" на "NetPeerTcpBinding" в файле конфигурации приложения, при этом не требуется изменять базу кода приложения.  
  
## <a name="see-also"></a>См. также  
 [Создание приложения одноранговых каналов](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
