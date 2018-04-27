---
title: Практическое руководство. Связывание с веб-службой с помощью компонента BindingSource в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00526e97c148fc4b587571993d2780d2e99f3ecc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="32f1a-102">Практическое руководство. Связывание с веб-службой с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32f1a-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="32f1a-103">Компонент <xref:System.Windows.Forms.BindingSource> можно использовать, если необходимо привязать элемент управления Windows Form к результатам вызова веб-служб XML. </span><span class="sxs-lookup"><span data-stu-id="32f1a-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="32f1a-104">Эта процедура аналогична привязке компонента <xref:System.Windows.Forms.BindingSource> к типу.</span><span class="sxs-lookup"><span data-stu-id="32f1a-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="32f1a-105">Необходимо создать клиентский прокси, который содержит методы и типы, предоставляемые веб-службой.</span><span class="sxs-lookup"><span data-stu-id="32f1a-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="32f1a-106">Клиентский прокси веб-службы можно создать либо непосредственно в самой веб-службе (ASMX-файл) или с помощью файла языка описания веб-служб (WSDL-файл).</span><span class="sxs-lookup"><span data-stu-id="32f1a-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="32f1a-107">Кроме того, клиентский прокси должен предоставлять доступ к полям сложных типов, используемых веб-службой, в виде общих свойств.</span><span class="sxs-lookup"><span data-stu-id="32f1a-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="32f1a-108">Затем <xref:System.Windows.Forms.BindingSource> привязывается к одному из типов, доступных в прокси веб-службы.</span><span class="sxs-lookup"><span data-stu-id="32f1a-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="32f1a-109">Создание и привязка к прокси на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="32f1a-109">To create and bind to a client-side proxy</span></span>  
  
1.  <span data-ttu-id="32f1a-110">Создайте форму Windows Forms в каталоге по своему усмотрению с подходящим пространством имен.</span><span class="sxs-lookup"><span data-stu-id="32f1a-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2.  <span data-ttu-id="32f1a-111">Добавьте в форму компонент <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="32f1a-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3.  <span data-ttu-id="32f1a-112">Откройте командную строку [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] и перейдите к каталогу, в котором расположена форма.</span><span class="sxs-lookup"><span data-stu-id="32f1a-112">Open the [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4.  <span data-ttu-id="32f1a-113">С помощью средства WSDL введите `wsdl` и URL-адрес для ASMX- или WSDL-файла веб-службы, пространство имен приложения и при необходимости язык, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="32f1a-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="32f1a-114">В следующем примере кода используется веб-службы, расположенной в http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx.</span><span class="sxs-lookup"><span data-stu-id="32f1a-114">The following code example uses the Web service located at http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx.</span></span> <span data-ttu-id="32f1a-115">Например, для C# типа `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` или для Visual Basic введите `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span><span class="sxs-lookup"><span data-stu-id="32f1a-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="32f1a-116">Передача пути в качестве аргумента для средства WSDL создаст клиентский прокси в том же каталоге и с тем пространством имен, что и у приложения, и на указанном языке.</span><span class="sxs-lookup"><span data-stu-id="32f1a-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="32f1a-117">Если вы используете [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], добавьте файл в проект.</span><span class="sxs-lookup"><span data-stu-id="32f1a-117">If you are using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], add the file to your project.</span></span>  
  
5.  <span data-ttu-id="32f1a-118">Выберите тип для привязки в клиентском прокси.</span><span class="sxs-lookup"><span data-stu-id="32f1a-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="32f1a-119">Обычно это тип, возвращаемый методом, предлагаемым веб-службой.</span><span class="sxs-lookup"><span data-stu-id="32f1a-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="32f1a-120">Поля выбранного типа должны предоставляться как общие свойства для привязки.</span><span class="sxs-lookup"><span data-stu-id="32f1a-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  <span data-ttu-id="32f1a-121">Задайте для свойства <xref:System.Windows.Forms.BindingSource.DataSource%2A> в <xref:System.Windows.Forms.BindingSource> нужный тип, содержащийся в клиентском прокси веб-службы.</span><span class="sxs-lookup"><span data-stu-id="32f1a-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="32f1a-122">Привязка элементов управления к компоненту BindingSource, который привязан к веб-службе</span><span class="sxs-lookup"><span data-stu-id="32f1a-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
-   <span data-ttu-id="32f1a-123">Привяжите элементы управления к <xref:System.Windows.Forms.BindingSource>, передав в качестве параметра общее свойство типа веб-службы.</span><span class="sxs-lookup"><span data-stu-id="32f1a-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="32f1a-124">Пример</span><span class="sxs-lookup"><span data-stu-id="32f1a-124">Example</span></span>  
 <span data-ttu-id="32f1a-125">В следующем примере кода показано, как привязать компонент <xref:System.Windows.Forms.BindingSource> к веб-службе, а затем привязать текстовое поле к компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="32f1a-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="32f1a-126">При нажатии кнопки вызывается метод веб-службы, результаты будут отображаться в `textbox1`.</span><span class="sxs-lookup"><span data-stu-id="32f1a-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32f1a-127">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="32f1a-127">Compiling the Code</span></span>  
 <span data-ttu-id="32f1a-128">Это завершенный пример, включающий метод `Main` и сокращенную версию кода клиентского прокси.</span><span class="sxs-lookup"><span data-stu-id="32f1a-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="32f1a-129">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="32f1a-129">This example requires:</span></span>  
  
-   <span data-ttu-id="32f1a-130">ссылки на сборки System, System.Drawing, System.Web.Services, System.Windows.Forms и System.XML.</span><span class="sxs-lookup"><span data-stu-id="32f1a-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="32f1a-131">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="32f1a-131">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="32f1a-132">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="32f1a-132">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="32f1a-133">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="32f1a-133">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f1a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="32f1a-134">See Also</span></span>  
 [<span data-ttu-id="32f1a-135">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="32f1a-135">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="32f1a-136">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32f1a-136">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
