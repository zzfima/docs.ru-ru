---
title: "Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation
В следующей процедуре в общих чертах описывается порядок переноса кода клиента веб\-службы ASP.NET на платформу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Процедура  
  
#### Миграция кода клиента службы ASP.NET в WCF  
  
1.  Убедитесь в наличии комплексного набора тестов для клиента.  
  
2.  С помощью Visual Studio 2005 обновите клиентское приложение до .NET 2.0.Выполните набор тестов.  
  
3.  Удалите код клиента ASP.NET из клиентского проекта.Этот код находится в модулях, сформированных с помощью программы WSDL.exe.  
  
4.  Сформируйте код клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).Добавьте этот код в клиентский проект и объедините полученную конфигурацию с существующим файлом конфигурации клиента.  
  
5.  Скомпилируйте приложение.Исправьте ошибки компиляции, заменив ссылки на старые клиентские типы ASP.NET ссылками на новые клиентские типы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
6.  Выполните набор тестов.  
  
## См. также  
 [Практическое руководство. Миграция кода веб\-службы ASP.NET на платформу Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)