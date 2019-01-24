---
title: Как выполнить Создание приложения асинхронной Windows Presentation Framework (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 89a4d1c244e69098971e87957f308f9a30ade6d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676644"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Как выполнить Создание приложения асинхронной Windows Presentation Framework (WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют привязать данные, полученные из службы данных, к элементам пользовательского интерфейса в приложении Windows Presentation Framework (WPF). Дополнительные сведения см. в разделе [привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Также можно выполнять операции в службе данных асинхронно, что позволяет приложению продолжать реагировать во время ожидания ответа на запрос службы данных. Приложения Silverlight обязаны обращаться к службе данных асинхронно. Дополнительные сведения см. в разделе [асинхронных операций](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Этот раздел описывает асинхронное обращение к службе данных и привязку результатов к элементам приложения WPF. Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен код на языке XAML, который определяет окно в приложении WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Пример  
 Следующая страница с выделенным кодом для файла XAML выполняет асинхронный запрос с использованием службы данных и привязывает результаты к элементам в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>См. также
- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
