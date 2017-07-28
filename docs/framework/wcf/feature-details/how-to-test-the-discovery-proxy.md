---
title: "Как проверить прокси-сервер обнаружения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Как проверить прокси-сервер обнаружения
Это последний из четырех разделов, в которых демонстрируется реализация прокси\-сервера обнаружения.  В предыдущем разделе [Как реализовать клиентское приложение, которое для поиска служб использует прокси\-сервер обнаружения](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md) было реализовано клиентское приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которое при помощи прокси\-сервера обнаружения находило и вызывало службу.  В данном разделе показано, как проверить работу прокси\-сервера обнаружения, службы и клиентского приложения.  
  
### Запуск прокси\-сервера обнаружения  
  
1.  Откройте командную строку от имени учетной записи администратора.  
  
2.  Может появиться диалоговое окно с сообщением «Брандмауэр Windows заблокировал некоторые из функций этой программы».  В этом случае нажмите кнопку **Разблокировать**.  
  
3.  Запустите из командной строки прокси\-сервер обнаружения DiscoveryProxy.exe.  
  
4.  Приложение должно вывести на экран сообщение: `Proxy started. Hit Enter to exit`.  
  
### Запуск обнаруживаемой службы  
  
1.  Откройте командную строку от имени учетной записи администратора.  
  
2.  Из командной строки запустите обнаруживаемую службу Service.exe.  
  
3.  Программа DiscoveryProxy.exe должна вывести на экран сообщение: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### Запуск клиентского приложения  
  
1.  Откройте окно командной строки.  
  
2.  Из командной строки запустите приложение client.exe.  
  
3.  Через несколько секунд клиентское приложение выведет на экран сообщение: «Connecting to \[Service\-Endpoint\]».  
  
4.  Программа service.exe должна затем вывести на экран сообщение: «Greeting request received, I will respond».  
  
5.  Приложение client.exe должно затем вывести на экран сообщение: «Hello Client\!»  
  
### Завершение работы приложений  
  
1.  Закройте клиентское приложение.  
  
2.  Завершите работу службы.  Прокси\-сервер обнаружения выведет на экран сообщение: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3.  Завершите работу прокси\-сервера обнаружения.  
  
## См. также  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [Как реализовать прокси\-сервера обнаружения](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)   
 [Как реализовать обнаружимую службу, которая регистрируется в прокси\-сервере обнаружения](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)   
 [Как реализовать клиентское приложение, которое для поиска служб использует прокси\-сервер обнаружения](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)