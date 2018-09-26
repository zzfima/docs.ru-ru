---
title: Индекс образцов кода WIF
ms.date: 03/30/2017
ms.assetid: 6711f01a-4743-43ce-95ab-5e2302a363ea
author: BrucePerlerMS
ms.openlocfilehash: b4c73bac9ddda83d78a4d9c95e3864d8d4e8ec4e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200091"
---
# <a name="wif-code-sample-index"></a>Индекс образцов кода WIF
Ниже приведены образцы кода для Windows Identity Foundation 4.5.  
  
-   [ClaimsAwareWebApp](https://go.microsoft.com/fwlink/?LinkID=248405) — этот образец демонстрирует основные принципы экспорта проверки подлинности (в локальную тестовую службу маркеров безопасности из средства Identity and Access Tool для Visual Studio 11) в классическом приложении ASP.NET (а не на веб-сайте).  
  
-   [ClaimsAwareWebService](https://go.microsoft.com/fwlink/?LinkID=248406) — этот образец демонстрирует основные принципы экспорта проверки подлинности в классической службе WCF.  
  
-   [ClaimsAwareMvcApplication](https://go.microsoft.com/fwlink/?LinkID=248407) — в этом примере демонстрируется интеграция WIF с MVC, включая направленную защиту и код, в котором учитываются перенаправления проверки подлинности на основе форм из контроллера LogOn.  
  
-   [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) — в этом примере демонстрируется готовый к применению в ферме кэш сеанса (вместо tokenreplycache), который позволяет использовать сеансы по ссылке, а не обмениваться большими файлами cookie. Также показан более простой способ защиты файлов cookie в ферме.  
  
-   [ClaimsAwareFormsAuthentication](https://go.microsoft.com/fwlink/?LinkID=248409) — в этом очень простом примере показано, что в .NET 4.5 вы получаете утверждения в субъектах вне зависимости от способа проверки подлинности пользователей.  
  
-   [ClaimsBasedAuthorization](https://go.microsoft.com/fwlink/?LinkID=248410) — в этих примерах показано, как использовать класс CLaimsAuthorizationManager и модуль ClaimsAuthorizationModule для применения собственных политик авторизации.  
  
-   [FederationMetadata](https://go.microsoft.com/fwlink/?LinkID=248411) — в этом примере демонстрируются как динамическое создание (в пользовательской службе STS), так и динамическое потребление (в приложении проверяющей стороны) документов метаданных.  
  
-   [CustomToken](https://go.microsoft.com/fwlink/?LinkID=248412) — этот образец демонстрирует создание пользовательского типа токена Simple Web Token (SWT).  
  
## <a name="see-also"></a>См. также  
 [Windows Identity Foundation](../../../docs/framework/security/index.md)
