---
title: "Обнаружение WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "обнаружение [WCF]"
  - "WCF [WCF], обнаружение"
  - "Windows Communication Foundation [WCF], обнаружение"
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Обнаружение WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] обеспечивает поддержку включения обнаружения служб во время выполнения совместимым способом с помощью протокола WS\-Discovery.Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут объявлять свою доступность компьютерам в сети с помощью многоадресного сообщения или прокси\-серверу обнаружения.Клиентские приложения могут осуществлять поиск служб, отвечающих набору указанных критериев, в сети или на прокси\-сервере обнаружения.В подразделах этого раздела представлены общие сведения и описание модели программирования данной функции.  
  
## В этом подразделе  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 Общие сведения о поддержке WS\-Discovery в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Модель объектов обнаружения WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 Содержит описание классов объектной модели и расширяемости поддержки WS\-Discovery.  
  
 [Как программно добавить возможность обнаружения к службе и клиенту WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Показано, как сделать службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] доступной для обнаружения.  
  
 [Реализация прокси\-сервера обнаружения](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 Содержит описание шагов, необходимых для реализации прокси\-сервера обнаружения, службы, доступной для обнаружения, которая регистрируется на прокси\-сервере обнаружения, и клиента, использующего прокси\-сервер обнаружения для поиска этой службы.  
  
 [Управление версиями обнаружения](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 Содержит общие сведения о реализации прототипа некоторых новых функций обнаружения.Также приводятся общие сведения о выборе версии обнаружения.  
  
 [Настройка обнаружения в файле конфигурации](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 Настройка обнаружения в файле конфигурации.  
  
 [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 Демонстрирует процесс использования клиентского канала обнаружения при записи клиентского приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].