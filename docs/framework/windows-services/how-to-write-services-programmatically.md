---
title: Как выполнить Создание службы программным способом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 70a2c184e7b39af7b4f0466ac9ac627cff98f0c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672916"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="8ba54-102">Как выполнить Создание службы программным способом</span><span class="sxs-lookup"><span data-stu-id="8ba54-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="8ba54-103">Если вы решили не использовать шаблон проекта "Служба Windows", для создания собственной службы вам придется настроить наследование и другие элементы инфраструктуры самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="8ba54-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="8ba54-104">Создавая службу программным способом, вам необходимо выполнить несколько действий, которые в случае с шаблоном выполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="8ba54-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="8ba54-105">Для класса службы необходимо настроить наследование от класса <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="8ba54-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="8ba54-106">Для проекта службы необходимо создать метод `Main`, который определяет запускаемые службы и вызывает для них метод <xref:System.ServiceProcess.ServiceBase.Run%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ba54-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="8ba54-107">Необходимо переопределить процедуры <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> и добавить код, который они должны выполнять.</span><span class="sxs-lookup"><span data-stu-id="8ba54-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="8ba54-108">Создание службы программным способом</span><span class="sxs-lookup"><span data-stu-id="8ba54-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="8ba54-109">Создайте пустой проект, а затем создайте ссылку на необходимые пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8ba54-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="8ba54-110">В окне **Обозреватель решений** щелкните правой кнопкой мыши узел **Ссылки** и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="8ba54-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="8ba54-111">На вкладке **.NET Framework** найдите **System.dll** и щелкните **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="8ba54-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="8ba54-112">Найдите **System.ServiceProcess.dll** и щелкните **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="8ba54-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="8ba54-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8ba54-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="8ba54-114">Добавьте класс и настройте для него наследование от <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="8ba54-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="8ba54-115">Настройте класс службы, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="8ba54-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="8ba54-116">Создайте для класса метод `Main` и с его помощью определите службы, которые будет содержать класс. `userService1` — имя класса.</span><span class="sxs-lookup"><span data-stu-id="8ba54-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="8ba54-117">Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и укажите обработку, которая должна выполняться при запуске службы.</span><span class="sxs-lookup"><span data-stu-id="8ba54-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="8ba54-118">Переопределите все прочие методы, для которых нужно задать определенную обработку, и напишите код, благодаря которому служба будет понимать, что нужно делать в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="8ba54-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="8ba54-119">Добавить установщики, необходимые для приложения службы.</span><span class="sxs-lookup"><span data-stu-id="8ba54-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="8ba54-120">Дополнительные сведения см. в разделе [Как Добавление установщиков в приложение-службу](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="8ba54-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="8ba54-121">Скомпилируйте проект, выбрав в меню **Сборка** пункт **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="8ba54-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ba54-122">Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.</span><span class="sxs-lookup"><span data-stu-id="8ba54-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="8ba54-123">Создайте проект установки и настраиваемые действия для установки службы.</span><span class="sxs-lookup"><span data-stu-id="8ba54-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="8ba54-124">Пример см. в разделе [Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8ba54-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="8ba54-125">Установите службу.</span><span class="sxs-lookup"><span data-stu-id="8ba54-125">Install the service.</span></span> <span data-ttu-id="8ba54-126">Дополнительные сведения см. в разделе [Как Установка и удаление служб](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="8ba54-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba54-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8ba54-127">See also</span></span>
- [<span data-ttu-id="8ba54-128">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="8ba54-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="8ba54-129">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="8ba54-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="8ba54-130">Практическое руководство. Добавление установщиков в приложение-службу</span><span class="sxs-lookup"><span data-stu-id="8ba54-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="8ba54-131">Практическое руководство. Запись сведений о службах в журнал</span><span class="sxs-lookup"><span data-stu-id="8ba54-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)
- [<span data-ttu-id="8ba54-132">Пошаговое руководство: Создание приложения служб Windows в конструкторе компонентов</span><span class="sxs-lookup"><span data-stu-id="8ba54-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
