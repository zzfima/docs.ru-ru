---
title: "Практическое руководство. Добавление установщиков в приложение служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 0dcb666f317ab285ae0156d2df16947f71665aee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="08023-102">Практическое руководство. Добавление установщиков в приложение служб</span><span class="sxs-lookup"><span data-stu-id="08023-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="08023-103">В состав Visual Studio входят компоненты установки, которые можно установить ресурсы, связанные с приложениями служб.</span><span class="sxs-lookup"><span data-stu-id="08023-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="08023-104">Компоненты установки регистрируются в качестве отдельных службы в системе, к которой он устанавливается и.</span><span class="sxs-lookup"><span data-stu-id="08023-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="08023-105">При работе с приложением службы, можно выбрать ссылку в окне «Свойства» для автоматического добавления соответствующих установщиков в проекте.</span><span class="sxs-lookup"><span data-stu-id="08023-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08023-106">Значения свойств службы копируются из класса службы в класс установщика.</span><span class="sxs-lookup"><span data-stu-id="08023-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="08023-107">При обновлении значения свойств в классе службы, они не обновляются автоматически в программу установки.</span><span class="sxs-lookup"><span data-stu-id="08023-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="08023-108">При добавлении установщика в проект новый класс (которая, по умолчанию называется `ProjectInstaller`) создается в проекте, а экземпляры установку компонентов создаются внутри него.</span><span class="sxs-lookup"><span data-stu-id="08023-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="08023-109">Этот класс служит центральной точки для всех компонентов установки проекту требуется.</span><span class="sxs-lookup"><span data-stu-id="08023-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="08023-110">Например если добавить второй службы в приложение и нажмите кнопку Добавить установщик, второй класс установщика не создается; Вместо этого в существующий класс добавляется дополнительный компонент установки для второй службы.</span><span class="sxs-lookup"><span data-stu-id="08023-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="08023-111">Необходимо сделать любое специальное кодирование установщиков для правильной установки служб.</span><span class="sxs-lookup"><span data-stu-id="08023-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="08023-112">Однако иногда может потребоваться изменить содержимое установщики, если вам нужно добавить специальные функции в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="08023-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08023-113">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="08023-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="08023-114">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="08023-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="08023-115">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="08023-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="08023-116">Добавление установщиков в приложение службы</span><span class="sxs-lookup"><span data-stu-id="08023-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="08023-117">В **обозревателе решений**, доступ **разработки** представление для службы, для которого требуется добавить компонент установки.</span><span class="sxs-lookup"><span data-stu-id="08023-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="08023-118">Щелкните фон конструктора, чтобы выбрать службу себе, а не его элементов.</span><span class="sxs-lookup"><span data-stu-id="08023-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="08023-119">С помощью конструктора в фокус, щелкните правой кнопкой мыши и выберите команду **Добавить установщик**.</span><span class="sxs-lookup"><span data-stu-id="08023-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="08023-120">Новый класс `ProjectInstaller`и два компонента установки <xref:System.ServiceProcess.ServiceProcessInstaller> и <xref:System.ServiceProcess.ServiceInstaller>, добавляются к проекту и значения свойств для службы будут скопированы в компоненты.</span><span class="sxs-lookup"><span data-stu-id="08023-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="08023-121">Нажмите кнопку <xref:System.ServiceProcess.ServiceInstaller> компонента и убедитесь, что значение <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> задано значение совпадает со значением <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> свойство самой службы.</span><span class="sxs-lookup"><span data-stu-id="08023-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="08023-122">Чтобы определить, как будет запущена служба, щелкните <xref:System.ServiceProcess.ServiceInstaller> компонента и задать <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> свойства соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="08023-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="08023-123">Значение</span><span class="sxs-lookup"><span data-stu-id="08023-123">Value</span></span>|<span data-ttu-id="08023-124">Результат</span><span class="sxs-lookup"><span data-stu-id="08023-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="08023-125">Служба должна быть запущена вручную после установки.</span><span class="sxs-lookup"><span data-stu-id="08023-125">The service must be manually started after installation.</span></span> <span data-ttu-id="08023-126">Дополнительные сведения см. в разделе [как: запуск служб](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="08023-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="08023-127">Служба будет запускаться сама при перезагрузке компьютера.</span><span class="sxs-lookup"><span data-stu-id="08023-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="08023-128">Не удается запустить службу.</span><span class="sxs-lookup"><span data-stu-id="08023-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="08023-129">Чтобы определить контекст безопасности, в котором будет выполняться служба, щелкните <xref:System.ServiceProcess.ServiceProcessInstaller> компонента и задайте соответствующие значения свойств.</span><span class="sxs-lookup"><span data-stu-id="08023-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="08023-130">Дополнительные сведения см. в разделе [как: укажите контекст безопасности для службы](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span><span class="sxs-lookup"><span data-stu-id="08023-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="08023-131">Переопределите все методы, для которых необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="08023-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="08023-132">Повторите шаги 1 – 7 для каждой дополнительной службы в проекте.</span><span class="sxs-lookup"><span data-stu-id="08023-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08023-133">Для каждой дополнительной службы в проекте, необходимо добавить дополнительный <xref:System.ServiceProcess.ServiceInstaller> компонента в проект `ProjectInstaller` класса.</span><span class="sxs-lookup"><span data-stu-id="08023-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="08023-134"><xref:System.ServiceProcess.ServiceProcessInstaller> Компонент, добавленный на третьем шаге работает со всеми отдельными установщиками служб в проекте.</span><span class="sxs-lookup"><span data-stu-id="08023-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08023-135">См. также</span><span class="sxs-lookup"><span data-stu-id="08023-135">See Also</span></span>  
 [<span data-ttu-id="08023-136">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="08023-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="08023-137">Практическое руководство. Установка и удаление служб</span><span class="sxs-lookup"><span data-stu-id="08023-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="08023-138">Практическое руководство. Запуск служб</span><span class="sxs-lookup"><span data-stu-id="08023-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="08023-139">Практическое руководство. Назначение службам контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="08023-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
