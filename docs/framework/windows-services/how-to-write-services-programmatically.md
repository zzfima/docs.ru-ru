---
title: "Практическое руководство. Создание службы программным способом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 1721417b8d1fc799e6af5d09762ee852d9fbfb03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="c1460-102">Практическое руководство. Создание службы программным способом</span><span class="sxs-lookup"><span data-stu-id="c1460-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="c1460-103">Если вы решили не использовать шаблон проекта службы Windows, можно написать собственные службы, задав порядок наследования и другие элементы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="c1460-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="c1460-104">При создании службы программными средствами, необходимо выполнить несколько шагов, которые шаблон, в противном случае будет обрабатываться автоматически:</span><span class="sxs-lookup"><span data-stu-id="c1460-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="c1460-105">Класс службы необходимо настроить для наследования от <xref:System.ServiceProcess.ServiceBase> класса.</span><span class="sxs-lookup"><span data-stu-id="c1460-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="c1460-106">Необходимо создать `Main` проект службы, который определяет запуск служб и вызывает метод <xref:System.ServiceProcess.ServiceBase.Run%2A> их метод.</span><span class="sxs-lookup"><span data-stu-id="c1460-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="c1460-107">Необходимо переопределить <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> процедуры и заполните поля на любой код, необходимо их запуска.</span><span class="sxs-lookup"><span data-stu-id="c1460-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="c1460-108">Чтобы создать службу программными средствами</span><span class="sxs-lookup"><span data-stu-id="c1460-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="c1460-109">Создайте пустой проект и ссылку на необходимые пространства имен, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c1460-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="c1460-110">В **обозревателе решений**, щелкните правой кнопкой мыши **ссылки** и выберите команду **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="c1460-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="c1460-111">На **.NET Framework** перейдите к **System.dll** и нажмите кнопку **выберите**.</span><span class="sxs-lookup"><span data-stu-id="c1460-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="c1460-112">Перейдите к пункту **System.ServiceProcess.dll** и нажмите кнопку **выберите**.</span><span class="sxs-lookup"><span data-stu-id="c1460-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="c1460-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c1460-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="c1460-114">Добавьте класс и настройте его для наследования от <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="c1460-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="c1460-115">Добавьте следующий код, чтобы настроить класс службы.</span><span class="sxs-lookup"><span data-stu-id="c1460-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="c1460-116">Создание `Main` классе, метод и использовать его для определения службы, будет содержать класс; `userService1` имя класса:</span><span class="sxs-lookup"><span data-stu-id="c1460-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="c1460-117">Переопределить <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода и определить, какой-либо обработки, будет выполняться при запуске службы.</span><span class="sxs-lookup"><span data-stu-id="c1460-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="c1460-118">Переопределите все прочие методы, необходимые для определения пользовательской обработки для и написать код, чтобы определить действия, которые следует предпринять службы в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="c1460-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="c1460-119">Добавить установщики, необходимые для приложения службы.</span><span class="sxs-lookup"><span data-stu-id="c1460-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="c1460-120">Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="c1460-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="c1460-121">Постройте проект, выбрав **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="c1460-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c1460-122">Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.</span><span class="sxs-lookup"><span data-stu-id="c1460-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="c1460-123">Создайте проект установки и настраиваемых действий для установки службы.</span><span class="sxs-lookup"><span data-stu-id="c1460-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="c1460-124">Пример см. в разделе [Пошаговое руководство: Создание приложения службы Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c1460-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="c1460-125">Установите службу.</span><span class="sxs-lookup"><span data-stu-id="c1460-125">Install the service.</span></span> <span data-ttu-id="c1460-126">Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1460-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1460-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c1460-127">See Also</span></span>  
 [<span data-ttu-id="c1460-128">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="c1460-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="c1460-129">Как: создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="c1460-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="c1460-130">Как: добавление установщиков в приложение службы</span><span class="sxs-lookup"><span data-stu-id="c1460-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="c1460-131">Как: журнал информации о службах</span><span class="sxs-lookup"><span data-stu-id="c1460-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="c1460-132">Пошаговое руководство: Создание приложения службы Windows в конструкторе компонентов</span><span class="sxs-lookup"><span data-stu-id="c1460-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
