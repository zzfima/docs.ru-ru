---
title: "Практическое руководство. Создание асинхронного приложения Windows Presentation Framework (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52e952abc6f1b47d9caf7a5583bb591c51a70dde
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Практическое руководство. Создание асинхронного приложения Windows Presentation Framework (службы данных WCF)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют привязать данные, полученные из службы данных, к элементам пользовательского интерфейса в приложении Windows Presentation Framework (WPF). Дополнительные сведения см. в разделе [привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Можно также выполнять операции службой данных в асинхронном режиме, что позволяет приложению продолжать отвечать во время ожидания ответа на запрос службы данных. Приложения Silverlight обязаны обращаться к службе данных асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Этот раздел описывает асинхронное обращение к службе данных и привязку результатов к элементам приложения WPF. Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен код на языке XAML, который определяет окно в приложении WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Пример  
 Следующая страница с выделенным кодом для файла XAML выполняет асинхронный запрос с использованием службы данных и привязывает результаты к элементам в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
