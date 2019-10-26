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
ms.openlocfilehash: 72638101b73e6b43fa225885b2e1f27d87b22826
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920148"
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
  
 Затем вызывается метод веб-службы и задается <xref:System.Windows.FrameworkElement.DataContext%2A> соответствующего элемента управления или окна в возвращаемый объект. Метод **WebMethod** службы MTPS принимает ссылку на объект **жетконтентрекуест** . Поэтому в следующем примере сначала настраивается объект запроса:  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 После установки <xref:System.Windows.FrameworkElement.DataContext%2A> можно создать привязки к свойствам объекта, для которого <xref:System.Windows.FrameworkElement.DataContext%2A> было установлено значение. В этом примере для <xref:System.Windows.FrameworkElement.DataContext%2A> задается объект **жетконтентреспонсе** **, возвращаемый методом GetObject** . В следующем примере <xref:System.Windows.Controls.ItemsControl> привязывается к и отображает значения **языкового стандарта** **аваилаблеверсионсандлокалес** из **жетконтентреспонсе**.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Сведения о структуре **жетконтентреспонсе**см. в [документации по службе содержимого](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](data-binding-overview.md)
- [Общие сведения об источниках привязки](binding-sources-overview.md)
- [Обеспечение доступности данных для привязки в XAML](how-to-make-data-available-for-binding-in-xaml.md)
