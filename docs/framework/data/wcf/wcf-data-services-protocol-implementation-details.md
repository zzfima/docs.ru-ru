---
title: "Сведения о реализации протокола служб данных WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 97c45e044bf5ae8e3afa56b06b253a43fbb95f83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Сведения о реализации протокола служб данных WCF
## <a name="odata-protocol-implementation-details"></a>Сведения о реализации протокола OData  
 Для [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] требуется, чтобы служба данных, которая реализует протокол, предоставляла определенный минимальный набор функциональных возможностей. Эти возможности описаны в документации по протоколу в терминах «должно» и «обязательно». Другие дополнительные функциональные возможности описаны в терминах «может». В данной статье описаны дополнительные функциональны возможности в текущий момент не реализованы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Дополнительные сведения см. в разделе [документации по протоколу OData](http://go.microsoft.com/fwlink/?LinkID=184554).  
  
### <a name="support-for-the-format-query-option"></a>Поддержка параметра запроса $format  
 Протокол [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] поддерживает как каналы JavaScript Notation (JSON), так и веб-каналы Atom, и [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставляет системный параметр запроса `$format`, чтобы клиент мог запрашивать формат ответного канала. Этот системный параметр запроса, если он поддерживается службой данных, должен переопределять значение заголовка Accept запроса. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] обеспечивает возвращение как каналов JSON, так и веб-каналов Atom. Однако реализация по умолчанию не поддерживает параметр запроса `$format` и использует только значение заголовка Accept для определения формата ответа. Бывают случаи, когда службе данных необходимо поддерживать параметр запроса `$format`, например когда клиенты не могут задать заголовок Accept. В этом случае необходимо расширить службы данных для обработки этого параметра в URI. Эти функции можно добавить к службе данных, загрузив [JSONP и формата управления URL-адрес поддержки для служб данных ADO.NET](http://go.microsoft.com/fwlink/?LinkId=208228) образец проекта с веб-сайта MSDN Code Gallery и добавив его в проект службы данных. Данный образец показывает удаление параметра запроса `$format`, а заголовок Accept заменяется на `application/json`. Когда включается образец проекта и добавляется `JSONPSupportBehaviorAttribute` к классу службы данных, служба получает возможность обработать `$format` параметра запроса `$format=json`. Для обработки `$format=atom` или других пользовательских форматов необходима также дополнительная настройка этого образца проекта.  
  
## <a name="wcf-data-services-behaviors"></a>Поведение служб данных WCF  
 Следующие разновидности поведения [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] не определяются явно протоколом [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
### <a name="default-sorting-behavior"></a>Порядок сортировки по умолчанию  
 Если запрос, отправляемый в службу данных, включает системный параметр запроса `$top` или `$skip` и не включает системный параметр запроса `$orderby`, возвращаемый канал сортируется по ключевым свойствам в порядке возрастания. Это происходит потому, что упорядочение необходимо для правильного разбиения результатов на страницы. Для этого служба данных добавляет к запросу выражение упорядочения. Этот способ также используется в том случае, если в службе данных включено разбиение по страницам, управляемое сервером. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md). Чтобы контролировать порядок возвращаемый канал, следует включить `$orderby` в URI запроса.  
  
## <a name="see-also"></a>См. также  
 [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
