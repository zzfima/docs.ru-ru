---
title: Создание первой службы WCF на основе утверждений
ms.date: 03/30/2017
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
author: BrucePerlerMS
ms.openlocfilehash: 13a17473388582e5fa72cd8d335b6a05204ea509
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306618"
---
# <a name="building-my-first-claims-aware-wcf-service"></a>Создание первой службы WCF на основе утверждений
## <a name="applies-to"></a>Применение  
  
-   Windows Identity Foundation (WIF)  
  
-   Windows Communication Foundation (WCF)  
  
## <a name="overview"></a>Обзор  
 В этом разделе представлен сценарий создания служб WCF, поддерживающих утверждения, при помощи WIF. Обычно существует три участника сценария для веб-службы, поддерживающей утверждения: сама веб-служба, пользователь и служба маркеров безопасности (STS). Данный сценарий представлен на иллюстрации ниже:  
  
 ![Схема, показывающая компоненты WIF базовой утверждений виду службы WCF.](./media/building-my-first-claims-aware-wcf-service/windows-identify-foundation-basic-claims-aware-windows-communication-foundation-service.gif)  
  
1. Клиент службы WCF (который иногда называют агентом) использует WIF для отправки учетных данных в службу STS. После успешной аутентификации служба STS создает токен для данного агента.  
  
2. Агент отправляет токен, созданный STS, в службу WCF.  
  
3. Служба WCF, поддерживающая утверждения, настроена на доверие к службе STS и ее токенам. Служба WCF, поддерживающая утверждения, использует WIF для проверки и анализа токена. Разработчики используют соответствующий API-интерфейс WIF и типы, например **ClaimsPrincipal**, для удовлетворения потребностей приложения (например, внедрения авторизации).  
  
 WIF входит в пакет .NET Framework, начиная с версии .NET 4.5. Прямая доступность классов WIF на этой платформе обеспечивает гораздо более глубокую интеграцию удостоверения на базе утверждений с платформой .NET, благодаря которой использовать утверждения становится проще. Если используется WIF 4.5, то для того, чтобы приступить к разработке веб-приложений, поддерживающих утверждения, не требуется устанавливать никакие дополнительные компоненты. Классы WIF теперь распространяются на различные сборки, например System.Security.Claims, System.IdentityModel и System.IdentityModel.Services.  
  
 STS — это служба, использующая токены после успешной аутентификации. Microsoft предлагает две службы STS, соответствующие отраслевым стандартам:  
  
-   [Службы федерации Active Directory (AD FS) 2.0](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [Windows Azure Access Control Service (ACS)](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 AD FS 2.0 является компонентом решения Windows Server R2 и может использоваться в качестве службы STS для локальных сценариев. Контроль доступа Azure Active Directory (также называемый службой контроля доступа или ACS) — это облачная служба, входящая в состав Microsoft Azure. Для тестирования или обучения можно также использовать другие службы STS, создавая с их помощью приложения, поддерживающие утверждения. Например, можно использовать STS локальной разработки, который является частью [Identity and Access Tool для Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) которая доступна через Интернет.  
  
 Чтобы построить на основе утверждений первой службы WCF, с помощью WIF, см. в разделе [How To: Включение WIF для веб-службы приложения WCF](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md).
  
## <a name="see-also"></a>См. также

- [Приступая к работе с WIF](../../../docs/framework/security/getting-started-with-wif.md)
