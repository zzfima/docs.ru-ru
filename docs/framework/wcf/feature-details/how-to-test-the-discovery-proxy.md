---
title: "Как проверить прокси-сервер обнаружения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55a7fe72b34fc8c099d921e7e295c184817825a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-test-the-discovery-proxy"></a>Как проверить прокси-сервер обнаружения
Это последний из четырех разделов, в которых демонстрируется реализация прокси-сервера обнаружения. В предыдущем разделе [как: реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), можно реализовать [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы, а затем вызывает Служба. В данном разделе показано, как проверить работу прокси-сервера обнаружения, службы и клиентского приложения.  
  
### <a name="run-the-discovery-proxy"></a>Запуск прокси-сервера обнаружения  
  
1.  Откройте командную строку от имени учетной записи администратора.  
  
2.  Может появиться диалоговое окно с сообщением «Брандмауэр Windows заблокировал некоторые из возможностей этой программы». Если вы видите это сообщение, нажмите кнопку **Unblock** кнопки.  
  
3.  Запустите из командной строки прокси-сервер обнаружения DiscoveryProxy.exe.  
  
4.  Приложение должно вывести на экран сообщение: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Запуск обнаруживаемой службы  
  
1.  Откройте командную строку от имени учетной записи администратора.  
  
2.  Из командной строки запустите обнаруживаемую службу Service.exe.  
  
3.  Программа DiscoveryProxy.exe должна вывести следующий текст: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Запуск клиентского приложения  
  
1.  Откройте окно командной строки.  
  
2.  Из командной строки запустите приложение client.exe.  
  
3.  Через несколько секунд клиентское приложение выведет на экран сообщение: «Connecting to [Service-Endpoint]».  
  
4.  Программа service.exe должна затем вывести на экран сообщение: «Greeting request received, I will respond».  
  
5.  Приложение client.exe должно затем вывести на экран сообщение: «Hello Client!»  
  
### <a name="shut-down-the-applications"></a>Завершение работы приложений  
  
1.  Закройте клиентское приложение.  
  
2.  Завершите работу службы. Прокси-сервер обнаружения выведет на экран сообщение: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3.  Завершите работу прокси-сервера обнаружения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Как: реализация прокси-сервера обнаружения](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [Как: реализовать Обнаружимую службу, которая регистрирует с прокси-сервера обнаружения](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [Как: реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
