---
title: Как установить заголовки в клиентском запросе (службы WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 420b13df0cc9d3f89087e18b58a2b416ce0bab7f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975250"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Как установить заголовки в клиентском запросе (службы WCF Data Services)
При использовании клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для доступа к службе данных, которая поддерживает Open Data Protocol (OData), клиентская библиотека автоматически задает нужные заголовки HTTP в сообщениях запроса, отправляемых службе данных. Однако клиентская библиотека не может определить заголовки сообщений, которые необходимы в некоторых случаях, например когда службе данных требуется проверка подлинности на основе утверждений или файлы cookies. Дополнительные сведения см. в разделе [Securing WCF Data Services](securing-wcf-data-services.md#clientAuthentication). В этих случаях необходимо вручную установить заголовки сообщений в запросе перед отправкой. В примере в этом разделе показано, как обработать событие <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> и добавить новый заголовок в сообщение запроса перед его отправкой службе данных.  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md). Вы также можете использовать [учебную службу данных Northwind](https://go.microsoft.com/fwlink/?LinkId=187426) , опубликованную на веб-сайте OData. Этот образец службы данных доступен только для чтения, и попытка сохранить изменения возвращает ошибку. Образцы служб данных на веб-сайте OData допускают анонимную проверку подлинности.  
  
## <a name="example"></a>Пример  
 В следующем примере регистрируется обработчик для события <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>, после чего службе данных отправляется запрос.  
  
> [!NOTE]
> Если служба данных требует задавать заголовок сообщения вручную для каждого запроса, попробуйте зарегистрировать обработчик для события <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>, переопределив частичный метод `OnContextCreated` в контейнере сущностей, который представляет службу данных, то есть в данном примере `NorthwindEntities`.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>Пример  
 Следующей метод обрабатывает событие <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> и добавляет заголовок проверки подлинности в запрос.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>См. также

- [Защита служб WCF Data Services](securing-wcf-data-services.md)
- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
