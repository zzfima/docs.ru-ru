---
title: "Создание первого веб-приложения ASP.NET с поддержкой утверждений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
caps.latest.revision: 5
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: aa25f163199652618e35399c6548a9864a17370a
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a>Создание первого веб-приложения ASP.NET с поддержкой утверждений
## <a name="applies-to"></a>Применение  
  
-   Windows Identity Foundation (WIF)  
  
-   ASP.NET  
  
 В этом разделе представлен сценарий создания веб-приложений ASP.NET с учетом утверждений при помощи WIF. Обычно существует три участника сценария для приложения с учетом утверждений: само приложение, пользователь и служба маркеров безопасности (STS). Данный сценарий представлен на иллюстрации ниже:  
  
 ![Базовое веб-приложение WIF](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")  
  
1.  Приложение, поддерживающее утверждения, использует WIF для идентификации запросов, не прошедших аутентификацию, и для перенаправления этих запросов в STS.  
  
2.  Конечный пользователь предоставляет учетные данные в STS, и после успешной аутентификации STS назначает токен данному пользователю.  
  
3.  Из STS пользователь перенаправляется в приложение, поддерживающее утверждения, с определенным STS токеном в запросе.  
  
4.  Приложение, поддерживающее утверждения, настроено на доверие к службе STS и ее токенам. Приложение, поддерживающее утверждения, использует WIF для проверки и анализа токена. Разработчики используют соответствующий API-интерфейс WIF и типы, например **ClaimsPrincpal**, для удовлетворения потребностей приложения (например, внедрения авторизации).  
  
 WIF входит в пакет .NET Framework, начиная с версии .NET 4.5. Прямая доступность классов WIF на этой платформе обеспечивает гораздо более глубокую интеграцию удостоверения на базе утверждений с платформой .NET, благодаря которой использовать утверждения становится проще. Если используется WIF 4.5, то для того, чтобы приступить к разработке веб-приложений, поддерживающих утверждения, не требуется устанавливать никакие дополнительные компоненты. Классы WIF теперь распространяются на различные сборки, например System.Security.Claims, System.IdentityModel и System.IdentityModel.Services.  
  
 STS — это служба, использующая токены после успешной аутентификации. Microsoft предлагает две службы STS, соответствующие отраслевым стандартам:  
  
-   [Службы федерации Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)  
  
-   [Служба управления доступом Windows Azure (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).  
  
 AD FS 2.0 является компонентом решения Windows Server R2 и может использоваться в качестве службы STS для локальных сценариев. ACS — это облачная служба, предлагаемая в составе платформы Microsoft Azure. Для тестирования или обучения можно также использовать другие службы STS, создавая с их помощью приложения, поддерживающие утверждения. Например, можно использовать службу STS локальной разработки, входящую в средство [Identity and Access Tool для Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849), которое можно бесплатно загрузить из Интернета.  
  
 Чтобы создать первое приложение ASP.NET, поддерживающее утверждения, с помощью WIF, выполните инструкции, представленные в одном из нижеперечисленных разделов:  
  
-   [Практическое руководство. Создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с использованием WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с использованием WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [Практическое руководство. Создание приложения ASP.NET, поддерживающего утверждения, с использованием аутентификации](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с WIF](../../../docs/framework/security/getting-started-with-wif.md)

