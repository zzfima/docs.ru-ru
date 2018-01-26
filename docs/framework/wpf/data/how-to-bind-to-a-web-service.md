---
title: "Практическое руководство. Привязка к веб-службе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b035f5922722a05759ff1e13514cc760a57d668
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-web-service"></a>Практическое руководство. Привязка к веб-службе
В этом примере показано, как выполнить привязку для объектов, возвращенных вызовы метода веб-службы.  
  
## <a name="example"></a>Пример  
 В этом примере используется [MSDN или TechNet публикации системы () содержимым MTPS](http://go.microsoft.com/fwlink/?LinkId=95677) для получения списка языков, поддерживаемых в указанный документ.  
  
 Перед вызовом веб-службы необходимо создать ссылку на него. Для создания ссылки на веб-службу MTPS с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], выполните следующие действия:  
  
1.  Откройте проект в [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  Из **проекта** меню, нажмите кнопку **Add Web Reference**.  
  
3.  В диалоговом окне задайте **URL-адрес** для [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Нажмите клавишу **Go** и затем **добавить ссылку**.  
  
 Затем вызовите метод веб-службы и задайте <xref:System.Windows.FrameworkElement.DataContext%2A> соответствующий элемент управления или окна для возвращаемого объекта. **GetContent** метод службы MTPS принимает ссылку на **getContentRequest** объекта. Таким образом в следующем примере сначала устанавливается объект запроса:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 После <xref:System.Windows.FrameworkElement.DataContext%2A> было задано, можно создать привязку к свойствам объекта, <xref:System.Windows.FrameworkElement.DataContext%2A> ему было присвоено. В этом примере <xref:System.Windows.FrameworkElement.DataContext%2A> равно **getContentResponse** объект, возвращаемый **GetContent** метод. В следующем примере <xref:System.Windows.Controls.ItemsControl> связывает и отображает **языкового стандарта** значения **availableVersionsAndLocales** из **getContentResponse**.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Дополнительные сведения о структуре **getContentResponse**, в разделе [документации службы содержимого](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Обеспечение доступности данных для привязки в XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
