---
title: Настройка приложения
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 6fc33e7b114bb78f823575a2b456d601ae75db94
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937641"
---
# <a name="configuring-your-application"></a><span data-ttu-id="3e5ba-102">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="3e5ba-102">Configuring Your Application</span></span>
<span data-ttu-id="3e5ba-103">Windows Communication Foundation (WCF) использует систему конфигурации .NET и позволяет настраивать службы как на уровне компьютера, так и в области приложения.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="3e5ba-104">Параметры конфигурации, определенные WCF, находятся в группе разделов `<system.serviceModel>`.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="3e5ba-105">Дополнительные сведения о настройке службы WCF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3e5ba-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="3e5ba-106">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="3e5ba-106">Configuring Services</span></span>](../configuring-services.md)  
  
- [<span data-ttu-id="3e5ba-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3e5ba-107">\<system.serviceModel></span></span>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="3e5ba-108">Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="3e5ba-109">Дополнительные сведения о параметрах приложения в файлах конфигурации .NET см. в разделе [\<appSettings >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3e5ba-109">For more information about application settings in .NET configuration files, see [\<appSettings>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="3e5ba-110">Использование редактора конфигураций</span><span class="sxs-lookup"><span data-stu-id="3e5ba-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="3e5ba-111">[Средство редактора конфигурации WCF (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для служб WCF с помощью графического пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-111">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="3e5ba-112">С помощью этого средства можно управлять параметрами для привязок, поведения, служб и диагностики WCF без непосредственного редактирования XML-файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-112">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="3e5ba-113">Изменение файлов конфигурации в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e5ba-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="3e5ba-114">Чтобы изменить файл конфигурации проекта службы WCF в Visual Studio, щелкните его правой кнопкой мыши в **Обозреватель решений** и выберите пункт изменить пункт контекстного меню для **WCF config** .</span><span class="sxs-lookup"><span data-stu-id="3e5ba-114">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="3e5ba-115">Запустится [средство редактора конфигурации (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3e5ba-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3e5ba-116">Если вы изменяете файл конфигурации проекта веб-службы WCF в Visual Studio, щелкнув его правой кнопкой мыши в **Обозреватель решений**, обратите внимание на отсутствие пункта контекстного меню **изменить WCF config** .</span><span class="sxs-lookup"><span data-stu-id="3e5ba-116">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="3e5ba-117">Чтобы решить эту проблему, в меню **Сервис** выберите пункт **Редактор конфигурации службы WCF**.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="3e5ba-118">После этого можно щелкнуть правой кнопкой мыши файл конфигурации и выбрать пункт меню изменить контекст в **WCF** .</span><span class="sxs-lookup"><span data-stu-id="3e5ba-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5ba-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e5ba-119">See also</span></span>

- [<span data-ttu-id="3e5ba-120">Редактор конфигурации (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="3e5ba-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="3e5ba-121">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="3e5ba-121">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="3e5ba-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3e5ba-122">\<system.serviceModel></span></span>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
