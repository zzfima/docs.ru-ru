---
title: Практическое руководство. Задание заголовков в клиентском запросе (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 5a72b349526d5cbba229cba627c23b1b1b889678
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943931"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Практическое руководство. Задание заголовков в клиентском запросе (WCF Data Services)
При использовании клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для доступа к службе данных, которая поддерживает [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], клиентская библиотека автоматически устанавливает необходимые заголовки HTTP в запросах, отправляемых службе данных. Однако клиентская библиотека не может определить заголовки сообщений, которые необходимы в некоторых случаях, например когда службе данных требуется проверка подлинности на основе утверждений или файлы cookies. Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication). В этих случаях необходимо вручную установить заголовки сообщений в запросе перед отправкой. В примере в этом разделе показано, как обработать событие <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> и добавить новый заголовок в сообщение запроса перед его отправкой службе данных.  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Вы также можете использовать [учебную службу данных Northwind](https://go.microsoft.com/fwlink/?LinkId=187426) , опубликованную на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-сайте. Этот образец службы данных доступен только для чтения и попытка сохранить изменения возвращает ошибку. Образец служб данных на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-сайте разрешает анонимную проверку подлинности.  
  
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

- [Защита служб WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
