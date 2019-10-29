---
title: Практическое руководство. Привязка к веб-службе
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: d752f4815de16daa466302881116e80aceec6edf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040906"
---
# <a name="how-to-bind-to-a-web-service"></a>Практическое руководство. Привязка к веб-службе
В этом примере показано, как выполнить привязку к объектам, возвращаемым вызовами метода веб-службы.  
  
## <a name="example"></a>Пример  
 В этом примере используется [Служба содержимого MSDN/TechNet Publishing System (MTPS)](https://go.microsoft.com/fwlink/?LinkId=95677) для получения списка языков, поддерживаемых указанным документом.  
  
 Перед вызовом веб-службы необходимо создать ссылку на нее. Чтобы создать веб-ссылку на службу MTPS с помощью Visual Studio, выполните следующие действия.  
  
1. Откройте проект в Visual Studio.  
  
2. В меню **проект** выберите команду **Добавить веб-ссылку**.  
  
3. В диалоговом окне задайте для **URL-адреса** значение [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4. Нажмите **Go** , а затем — **Добавить ссылку**.  
  
 Затем вызывается метод веб-службы и задается <xref:System.Windows.FrameworkElement.DataContext%2A> соответствующего элемента управления или окна в возвращаемый объект. Метод `GetContent` службы MTPS принимает ссылку на объект `getContentRequest`. Поэтому в следующем примере сначала настраивается объект запроса:  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 После установки <xref:System.Windows.FrameworkElement.DataContext%2A> можно создать привязки к свойствам объекта, для которого <xref:System.Windows.FrameworkElement.DataContext%2A> было установлено значение. В этом примере <xref:System.Windows.FrameworkElement.DataContext%2A> задается как объект `getContentResponse`, возвращаемый методом `GetContent`. В следующем примере <xref:System.Windows.Controls.ItemsControl> привязывается к и отображает `locale` значения `availableVersionsAndLocales` `getContentResponse`.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Сведения о структуре `getContentResponse`см. в [документации по службе содержимого](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](data-binding-overview.md)
- [Общие сведения об источниках привязки](binding-sources-overview.md)
- [Обеспечение доступности данных для привязки в XAML](how-to-make-data-available-for-binding-in-xaml.md)
