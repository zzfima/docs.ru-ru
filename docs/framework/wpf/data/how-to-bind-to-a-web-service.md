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
ms.openlocfilehash: 3a3f6edc974448ddab9fe30e97bdc1130d3b97dc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449976"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="01558-102">Практическое руководство. Привязка к веб-службе</span><span class="sxs-lookup"><span data-stu-id="01558-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="01558-103">В этом примере показано, как выполнить привязку к объектам, возвращаемым вызовами метода веб-службы.</span><span class="sxs-lookup"><span data-stu-id="01558-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01558-104">Пример</span><span class="sxs-lookup"><span data-stu-id="01558-104">Example</span></span>  
 <span data-ttu-id="01558-105">В этом примере используется служба содержимого MSDN/TechNet Publishing System (MTPS) для получения списка языков, поддерживаемых указанным документом.</span><span class="sxs-lookup"><span data-stu-id="01558-105">This example uses the MSDN/TechNet Publishing System (MTPS) Content Service to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="01558-106">Перед вызовом веб-службы необходимо создать ссылку на нее.</span><span class="sxs-lookup"><span data-stu-id="01558-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="01558-107">Чтобы создать веб-ссылку на службу MTPS с помощью Visual Studio, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="01558-107">To create a Web reference to the MTPS service using Visual Studio, follow the following steps:</span></span>  
  
1. <span data-ttu-id="01558-108">Откройте проект в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="01558-108">Open your project in Visual Studio.</span></span>  
  
2. <span data-ttu-id="01558-109">В меню **проект** выберите команду **Добавить веб-ссылку**.</span><span class="sxs-lookup"><span data-stu-id="01558-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="01558-110">В диалоговом окне задайте для **URL-адреса** значение [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="01558-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="01558-111">Нажмите **Go** , а затем — **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="01558-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="01558-112">Затем вызывается метод веб-службы и задается <xref:System.Windows.FrameworkElement.DataContext%2A> соответствующего элемента управления или окна в возвращаемый объект.</span><span class="sxs-lookup"><span data-stu-id="01558-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="01558-113">Метод `GetContent` службы MTPS принимает ссылку на объект `getContentRequest`.</span><span class="sxs-lookup"><span data-stu-id="01558-113">The `GetContent` method of the MTPS service takes a reference to the `getContentRequest` object.</span></span> <span data-ttu-id="01558-114">Поэтому в следующем примере сначала настраивается объект запроса:</span><span class="sxs-lookup"><span data-stu-id="01558-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="01558-115">После установки <xref:System.Windows.FrameworkElement.DataContext%2A> можно создать привязки к свойствам объекта, для которого <xref:System.Windows.FrameworkElement.DataContext%2A> было установлено значение.</span><span class="sxs-lookup"><span data-stu-id="01558-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="01558-116">В этом примере <xref:System.Windows.FrameworkElement.DataContext%2A> задается как объект `getContentResponse`, возвращаемый методом `GetContent`.</span><span class="sxs-lookup"><span data-stu-id="01558-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the `getContentResponse` object returned by the `GetContent` method.</span></span> <span data-ttu-id="01558-117">В следующем примере <xref:System.Windows.Controls.ItemsControl> привязывается к и отображает `locale` значения `availableVersionsAndLocales` `getContentResponse`.</span><span class="sxs-lookup"><span data-stu-id="01558-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the `locale` values of `availableVersionsAndLocales` of `getContentResponse`.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="01558-118">Сведения о структуре `getContentResponse`см. в [документации по службе содержимого](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="01558-118">For information about the structure of `getContentResponse`, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01558-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="01558-119">See also</span></span>

- [<span data-ttu-id="01558-120">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="01558-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="01558-121">Общие сведения об источниках привязки</span><span class="sxs-lookup"><span data-stu-id="01558-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="01558-122">Обеспечение доступности данных для привязки в XAML</span><span class="sxs-lookup"><span data-stu-id="01558-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
