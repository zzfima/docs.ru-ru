---
title: "Как настроить режим привязки данных (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, настройка"
  - "Службы WCF Data Services, привязка данных"
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как настроить режим привязки данных (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют добавлять специализированную логику, которая вызывается коллекцией <xref:System.Data.Services.Client.DataServiceCollection%601> при добавлении или удалении объекта из коллекции привязок или при изменении значения свойства.  Специализированная логика представляется методами, на которые ссылаются делегаты <xref:System.Func%602>. Они возвращают значение `false`, если по завершении выполнения специализированного метода все еще необходимо применить режим по умолчанию, и `true`, если дальнейшая обработка события должна быть прекращена.  
  
 Примеры в этом разделе добавляют специализированные методы для обоих параметров `entityChanged` и `entityCollectionChanged` коллекции <xref:System.Data.Services.Client.DataServiceCollection%601>.  Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 Следующая страница с выделенным кодом для файла XAML создает коллекцию <xref:System.Data.Services.Client.DataServiceCollection%601> со специализированными методами, которые вызываются при внесении изменений в данные, привязанные к коллекции.  При возникновении события <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> добавленный метод предотвращает удаление из службы данных элемента, удаленного из коллекции привязок.  При возникновении события <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> значение `ShipDate` проверяется, чтобы изменения не проводились над заказами, которые уже были доставлены.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## Пример  
 Следующий код XAML определяет окно для предыдущего примера.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)