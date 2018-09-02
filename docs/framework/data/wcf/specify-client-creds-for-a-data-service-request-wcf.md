---
title: Как указать учетные данные клиента для запроса службы данных (службы WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
ms.openlocfilehash: d0fbf01de05a02c03782af9e392a79b6dd3e8bee
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402525"
---
# <a name="how-to-specify-client-credentials-for-a-data-service-request-wcf-data-services"></a>Как указать учетные данные клиента для запроса службы данных (службы WCF Data Services)
По умолчанию клиентская библиотека не поддерживает учетные данные при отправке запроса службе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Тем не менее можно задать отправку учетных данных для проверки подлинности запросов службе данных, указав <xref:System.Net.NetworkCredential> для свойства <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> в контексте <xref:System.Data.Services.Client.DataServiceContext>. Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md). В примере в этом разделе показано, как явно предоставить учетные данные, используемые клиентом [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] при запросе данных из службы данных.  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Можно также использовать [образца службы данных Northwind](https://go.microsoft.com/fwlink/?LinkId=187426) , опубликованный на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-сайта этот образец данных служба доступна только для чтения и попытка сохранить изменения возвращает ошибку. Образцы служб данных на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-сайт допускают анонимную проверку подлинности.  
  
## <a name="example"></a>Пример  
 Ниже приведен на странице кода для файла расширяемого языка разметки приложений (XAML), который представляет главную страницу приложения Windows Presentation Framework. В этом примере отображается экземпляр `LoginWindow`, получающий учетные данные у пользователя и использующий их при составлении запроса к службе данных.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentials.xaml.cs#clientcredentials)]  
 [!code-vb[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/clientcredentials.xaml.vb#clientcredentials)]
  
## <a name="example"></a>Пример  
 Ниже приведен код на языке XAML, который определяет основную страницу в WPF-приложении.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentials.xaml#clientcredentialsxaml)]  
  
## <a name="example"></a>Пример  
 Следующий пример взят из страницы с выделенным кодом для окна, которое используется для получения учетных данных проверки подлинности у пользователя, прежде чем отправить запрос службе данных.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentialslogin.xaml.cs#clientcredentialslogin)]  
 [!code-vb[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/clientcredentialslogin.xaml.vb#clientcredentialslogin)]
  
## <a name="example"></a>Пример  
 Ниже приведен код на языке XAML, который определяет имя входа в WPF-приложении.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsLoginXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentialslogin.xaml#clientcredentialsloginxaml)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 В отношении примера в этом разделе следует учитывать следующие рекомендации по безопасности.  
  
-   Чтобы убедиться, что учетные данные, предоставленные в этом образце, работоспособны, служба данных Northwind должна использовать схему проверки подлинности, отличную от анонимного доступа. В противном случае веб-узел, на котором размещена служба данных, не запросит учетные данные.  
  
-   Учетные данные пользователя должны запрашиваться только во время выполнения и не должны кэшироваться. Учетные данные следует хранить безопасным способом.  
  
-   Данные, отправляемые с помощью базовой и дайджест-аутентификации, не шифруются, поэтому злоумышленник может их видеть. Помимо этого, учетные данных обычной проверки подлинности (имя пользователя и пароль) отправляются открытым текстом и могут быть перехвачены.  
  
 Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Защита служб WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
