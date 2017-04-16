---
title: "Практическое руководство. Привязка к веб-службе | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязка данных, веб-служба"
  - "привязка данных, веб-служба"
  - "привязка веб-служб"
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Привязка к веб-службе
В этом примере демонстрируется привязка к объектам, возвращаемым при вызове методов веб\-служб.  
  
## Пример  
 В этом примере используется [Служба управления содержимым MSDN\/TechNet Publishing System \(MTPS\)](http://go.microsoft.com/fwlink/?LinkId=95677) для получения списка языков, поддерживаемых указанным документом.  
  
 Перед вызовом веб\-службы необходимо создать ссылку на нее.  Чтобы создать веб\-ссылку на службу MTPS с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], выполните следующие действия.  
  
1.  Откройте проект в [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  В меню **Проект** выберите команду **Добавить веб\-ссылку**.  
  
3.  В диалоговом окне установите **URL\-адрес** в значение [http:\/\/services.msdn.microsoft.com\/contentservices\/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Нажмите кнопку **Перейти**, а затем **Добавить ссылку**.  
  
 Далее вызовите метод веб\-службы и задайте для возвращаемого объекта <xref:System.Windows.FrameworkElement.DataContext%2A> соответствующего элемента управления или окна.  Метод **GetContent** службы MTPS принимает ссылку на объект **getContentRequest**.  Таким образом, в следующем примере сначала устанавливается объект запроса:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 После установки <xref:System.Windows.FrameworkElement.DataContext%2A> можно создать привязку к свойствам объекта, для которого было установлено <xref:System.Windows.FrameworkElement.DataContext%2A>.  В этом примере <xref:System.Windows.FrameworkElement.DataContext%2A> присваивается объекту **getContentResponse**, возвращенному методом **GetContent**.  В следующем примере <xref:System.Windows.Controls.ItemsControl> выполняет привязку к **locale** и отображает значения **availableVersionsAndLocales** для **getContentResponse**.  
  
 [!code-xml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Дополнительные сведения о структуре **getContentResponse** см. в разделе [Документация службы управления содержимым](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Обеспечение доступности данных для привязки в XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)