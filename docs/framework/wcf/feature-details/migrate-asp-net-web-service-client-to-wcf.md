---
title: "Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baf43f2bfa2175062c57f73e45835c251ac5769e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation
В следующей процедуре в общих чертах описывается порядок переноса кода клиента веб-службы ASP.NET на платформу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>Миграция кода клиента службы ASP.NET в WCF  
  
1.  Убедитесь в наличии комплексного набора тестов для клиента.  
  
2.  С помощью Visual Studio 2005 обновите клиентское приложение до .NET 2.0. Выполните набор тестов.  
  
3.  Удалите код клиента ASP.NET из клиентского проекта. Этот код находится в модулях, сформированных с помощью программы WSDL.exe.  
  
4.  Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] кода клиента с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Добавьте этот код в клиентский проект и объедините полученную конфигурацию с существующим файлом конфигурации клиента.  
  
5.  Скомпилируйте приложение. Исправьте ошибки компиляции, заменив ссылки на старые клиентские типы ASP.NET ссылками на новые клиентские типы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
6.  Выполните набор тестов.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
