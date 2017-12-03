---
title: "Общие сведения о синдикации WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af6d4c39-e5e8-4099-aee6-5261feff9107
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f1595cbb1d225e3dd4e73a354028745d4cd0428
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-syndication-overview"></a>Общие сведения о синдикации WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает экспонирование веб-каналов синдикации из службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Синдикация - это механизм интеграции приложения, суть которого в том, что сервер предоставляет некоторые данные приложения в формате с возможностью взаимодействия, называемом веб-канал. Веб-канал - это коллекция данных приложения, которая состоит из метаданных уровня веб-канала (название, автор, URL-адрес и другие метаданные) и серии элементов веб-канала. В пределах веб-канала эти элементы, как правило, упорядочены по времени (в обратном хронологическом порядке). Элемент веб-канала состоит из стандартного набора метаданных уровня элемента (название, URL-адрес, дата создания, категория и другие метаданные уровня элемента) и данных приложения произвольного размера. Двумя наиболее часто используемыми типами веб-каналов синдикации являются RSS (Really Simple Syndication) 2.0 и Atom 1.0, оба типа поддерживаются [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="object-model"></a>Объектная модель  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] определяет набор классов синдикации, которые позволяют работать с веб-каналами, элементами веб-каналов и связанными с ними метаданными независимо от формата: <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationPerson>, <xref:System.ServiceModel.Syndication.SyndicationLink>. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]также определяет классы инфраструктуры, созданных на основе модели программирования WCF REST для обеспечения поддержки синдикации, включая: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>, и <!--zz <xref:System.ServiceModel.Syndication.RSS20FeedFormatter>--> `RSS20FeedFormatter`. Классы модуля форматирования веб-каналов поддерживают сериализацию объектной модели в RSS 2.0 и Atom 1.0 и из них.  
  
## <a name="scenarios"></a>Сценарии  
 В настоящее время синдикация чаще всего используется при создании блогов, авторы которых периодически публикуют определенную информацию. Эта информация может представлять собой текст, изображения, звуковые файлы и многое другое. Многие газеты и журналы используют синдикацию для публикации новостей или статей. Подписавшись на такой веб-канал, пользователь может отслеживать появление на этих сайтах новой информации. Хотя синдикация чаще всего связана с блогами и издателями, ее можно использовать с любым приложением, предоставляющим коллекцию данных; так, с помощью веб-канала синдикации можно создать и обслуживать базу данных об ошибках. Можно создать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], предоставляющую операцию `CodeDefects`. Эта операция может содержать параметр, задающий адрес электронной почты пользователя, ошибки которого необходимо извлечь. Для вызова операции клиент может использовать следующий URL-адрес: http://someserver/bugDatabase/CodeDefects?user=johndoe.  
  
## <a name="syndication-formats"></a>Форматы синдикации  
 Платформа синдикации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает RSS 2.0 и Atom 1.0.  
  
## <a name="see-also"></a>См. также  
 [Модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
