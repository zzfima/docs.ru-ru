---
title: "Обнаружение WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fda50f14d9003b81f93840571b8b27f874f7730b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-discovery"></a>Обнаружение WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предоставляет поддержку для включения обнаружения служб во время выполнения совместимым способом с помощью протокола WS-Discovery. Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут сообщать о своей доступности компьютерам в сети с помощью многоадресного сообщения либо передавать сообщение прокси-серверу обнаружения. Клиентские приложения могут осуществлять поиск служб, отвечающих набору указанных критериев, в сети или на прокси-сервере обнаружения. В подразделах этого раздела представлены общие сведения и описание модели программирования данной возможности.  
  
## <a name="in-this-section"></a>Содержание  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 Общие сведения о поддержке WS-Discovery в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Модель объектов обнаружения WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 Содержит описание классов объектной модели и расширяемости поддержки WS-Discovery.  
  
 [Как: программно добавить возможность обнаружения службы WCF и клиент](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Показано, как сделать службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] доступной для обнаружения.  
  
 [Реализация прокси-сервера обнаружения](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 Содержит описание шагов, необходимых для реализации прокси-сервера обнаружения, службы, доступной для обнаружения, которая регистрируется на прокси-сервере обнаружения, и клиента, использующего прокси-сервер обнаружения для поиска этой службы.  
  
 [Управление версиями обнаружения](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 Содержит общие сведения о реализации прототипа некоторых новых возможностей обнаружения. Также приводятся общие сведения о выборе версии обнаружения.  
  
 [Настройка обнаружения в файле конфигурации](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 Настройка обнаружения в файле конфигурации.  
  
 [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 Демонстрирует процесс использования клиентского канала обнаружения при записи клиентского приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].
