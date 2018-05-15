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
ms.openlocfilehash: 75d9d5b6981f868c7a172edd7f23cf923fedd525
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="514c3-102">Практическое руководство. Привязка к веб-службе</span><span class="sxs-lookup"><span data-stu-id="514c3-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="514c3-103">В этом примере показано, как выполнить привязку для объектов, возвращенных вызовы метода веб-службы.</span><span class="sxs-lookup"><span data-stu-id="514c3-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="514c3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="514c3-104">Example</span></span>  
 <span data-ttu-id="514c3-105">В этом примере используется [MSDN или TechNet публикации системы () содержимым MTPS](http://go.microsoft.com/fwlink/?LinkId=95677) для получения списка языков, поддерживаемых в указанный документ.</span><span class="sxs-lookup"><span data-stu-id="514c3-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="514c3-106">Перед вызовом веб-службы необходимо создать ссылку на него.</span><span class="sxs-lookup"><span data-stu-id="514c3-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="514c3-107">Для создания ссылки на веб-службу MTPS с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="514c3-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="514c3-108">Откройте проект в [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="514c3-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="514c3-109">Из **проекта** меню, нажмите кнопку **Add Web Reference**.</span><span class="sxs-lookup"><span data-stu-id="514c3-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="514c3-110">В диалоговом окне задайте **URL-адрес** для [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="514c3-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="514c3-111">Нажмите клавишу **Go** и затем **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="514c3-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="514c3-112">Затем вызовите метод веб-службы и задайте <xref:System.Windows.FrameworkElement.DataContext%2A> соответствующий элемент управления или окна для возвращаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="514c3-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="514c3-113">**GetContent** метод службы MTPS принимает ссылку на **getContentRequest** объекта.</span><span class="sxs-lookup"><span data-stu-id="514c3-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="514c3-114">Таким образом в следующем примере сначала устанавливается объект запроса:</span><span class="sxs-lookup"><span data-stu-id="514c3-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="514c3-115">После <xref:System.Windows.FrameworkElement.DataContext%2A> было задано, можно создать привязку к свойствам объекта, <xref:System.Windows.FrameworkElement.DataContext%2A> ему было присвоено.</span><span class="sxs-lookup"><span data-stu-id="514c3-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="514c3-116">В этом примере <xref:System.Windows.FrameworkElement.DataContext%2A> равно **getContentResponse** объект, возвращаемый **GetContent** метод.</span><span class="sxs-lookup"><span data-stu-id="514c3-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="514c3-117">В следующем примере <xref:System.Windows.Controls.ItemsControl> связывает и отображает **языкового стандарта** значения **availableVersionsAndLocales** из **getContentResponse**.</span><span class="sxs-lookup"><span data-stu-id="514c3-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="514c3-118">Дополнительные сведения о структуре **getContentResponse**, в разделе [документации службы содержимого](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="514c3-118">For information about the structure of **getContentResponse**, see [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514c3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="514c3-119">See Also</span></span>  
 [<span data-ttu-id="514c3-120">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="514c3-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="514c3-121">Общие сведения об источниках привязки</span><span class="sxs-lookup"><span data-stu-id="514c3-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="514c3-122">Обеспечение доступности данных для привязки в XAML</span><span class="sxs-lookup"><span data-stu-id="514c3-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
