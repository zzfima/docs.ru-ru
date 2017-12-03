---
title: "Переход на платформу Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e27ee5f2e1b2ad042fd8c0104e89b99eb5e4bc96
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="adopting-windows-communication-foundation"></a>Переход на платформу Windows Communication Foundation
Можно использовать [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для новых разработок, продолжая поддерживать существующие приложения, разработанные с использованием ASP.NET. Поскольку среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] рассчитана на то, чтобы быть самым подходящим выбором для обеспечения взаимодействия с приложениями, созданными с помощью платформы .NET Framework в любом сценарии, она может выполнять роль стандартного инструмента для решения широкого круга проблем обмена данными между программами способами, недоступными в ASP.NET.  
  
 Новые приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно разворачивать на тех же компьютерах, что и существующие веб-службы ASP.NET. Если существующие веб-службы ASP.NET используют платформу .NET версии ниже 2.0, можно с помощью программы регистрации IIS для ASP.NET селективно развернуть платформу .NET Framework 2.0 для приложений IIS, в которых будут размещаться новые приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Это средство задокументирован по [средство регистрации ASP.NET IIS (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), и есть пользовательский интерфейс, встроенные в консоль управления IIS 6.0.  
  
 Платформу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно использовать для добавления новых функций к существующим веб-службам ASP.NET путем добавления служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], настроенных для работы в режиме совместимости с ASP.NET, в существующие приложения веб-служб ASP.NET в IIS. В режиме совместимости с ASP.NET код новых служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может получать доступ и обновлять ту же информацию о состоянии приложения, что и ранее существовавший код ASP.NET, за счет использования класса <xref:System.Web.HttpContext>. Приложения могут также совместно использовать одни и те же библиотеки классов.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиенты могут пользоваться веб-службами ASP.NET. Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], настроенные с <xref:System.ServiceModel.BasicHttpBinding>, могут использоваться с клиентами веб-служб ASP.NET. Веб-службы ASP.NET могут сосуществовать с приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно использовать даже для добавления функций в существующие веб-службы ASP.NET. Благодаря наличию всех этих способов совместного использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и веб-служб, миграция веб-служб ASP.NET в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может потребоваться только в случае, если нужны функции, предоставляемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и отсутствующие в веб-службах ASP.NET.  
  
 Однако в тех редких случаях, когда миграция необходима, следует учитывать, что перенос кода из одной технологии в другую редко является правильным подходом. Причина перехода на новую технологию заключается в необходимости удовлетворения новых требований, которые невозможно удовлетворить в рамках предыдущей технологии, поэтому в таком случае правильнее будет разработать новое решение, соответствующее новому расширенному набору требований. Новая разработка позволяет учесть опыт работы с существующей системой и знания, накопленные с момента создания этой системы. Новая разработка также позволит использовать все возможности новой технологии, а не просто воспроизводить старую систему на новой платформе. После создания прототипов ключевых элементов новой разработки будет проще заново использовать код существующей системы в новой системе.  
  
 Для немногочисленных случаев, когда правильным решением будет перенос веб-служб ASP.NET на платформу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в последующих разделах приведены некоторые рекомендации. Приводятся рекомендации о порядке миграции служб и порядке миграции клиентов.  
  
 Для полноты анализа по переносу существующих веб-служб ASP.NET в WCF см. в разделе [веб-служб ASP.NET и Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761). В данном разделе описывается порядок реализации совместимой службы WCF на основе метаданных для веб-службы ASP.NET, а также порядок миграции кода веб-службы и клиента ASP.NET в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>См. также  
 [Как: извлечение данных и реализация совместимой службы](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [Как: перенос кода службы ASP.NET на платформу Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [Как: Миграция кода клиента службы ASP.NET на платформу Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
