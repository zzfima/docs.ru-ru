---
title: "Как создать асинхронное приложение Windows Presentation Framework (службы WCF Data Services) | Microsoft Docs"
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
  - "Службы WCF Data Services, асинхронные операции"
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как создать асинхронное приложение Windows Presentation Framework (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют привязать данные, полученные из службы данных, к элементам пользовательского интерфейса в приложении Windows Presentation Framework \(WPF\).  Дополнительные сведения см. в разделе [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Кроме того, имеется возможность выполнять операции над службой данных асинхронно, что позволяет приложению продолжать реагировать на запросы пользователя в процессе ожидания ответа на запрос к службе данных.  Приложения Silverlight обязаны обращаться к службе данных асинхронно.  Для получения дополнительной информации см. [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Этот раздел описывает асинхронное обращение к службе данных и привязку результатов к элементам приложения WPF.  Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 Ниже приведен код на языке XAML, который определяет окно в приложении WPF.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## Пример  
 Следующая страница с выделенным кодом для файла XAML выполняет асинхронный запрос с использованием службы данных и привязывает результаты к элементам в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)