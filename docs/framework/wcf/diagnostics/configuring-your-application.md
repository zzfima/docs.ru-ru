---
title: "Настройка приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f22fac02616070ecd6498ad0e158782001681ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-your-application"></a><span data-ttu-id="ba7e7-102">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="ba7e7-102">Configuring Your Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ba7e7-103"> использует систему конфигурации .NET и позволяет настраивать службы и на компьютере, и в области приложений.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-103"> uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="ba7e7-104">Параметры конфигурации, определяемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], находятся в группе разделов `<system.serviceModel>`.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ba7e7-105"> том, как настроить службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ba7e7-105"> how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="ba7e7-106">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="ba7e7-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="ba7e7-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba7e7-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="ba7e7-108">Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ba7e7-109">в разделе параметров приложения в файлах конфигурации .NET, [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).</span><span class="sxs-lookup"><span data-stu-id="ba7e7-109"> application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="ba7e7-110">Использование редактора конфигураций</span><span class="sxs-lookup"><span data-stu-id="ba7e7-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="ba7e7-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы с помощью графического интерфейса пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="ba7e7-112">С помощью этого средства можно управлять параметрами привязок, поведений, служб и диагностики [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без непосредственного изменения XML-файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="ba7e7-113">Изменение файлов конфигурации в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ba7e7-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="ba7e7-114">Чтобы изменить файл конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проект службы в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], щелкните его правой кнопкой мыши **обозревателе решений** и выберите **изменить конфигурацию WCF** пункт контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="ba7e7-115">Будет запущен [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ba7e7-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba7e7-116">Если изменить файл конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проекта веб-службы в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] щелкнув его в **обозревателе решений**, обратите внимание, что **изменить конфигурацию WCF** отсутствует пункт контекстного меню .</span><span class="sxs-lookup"><span data-stu-id="ba7e7-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="ba7e7-117">Чтобы обойти эту проблему, щелкните **средства** меню и выберите **Редактор конфигураций служб WCF**.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="ba7e7-118">После этого щелкните правой кнопкой мыши файл конфигурации и использовать **изменить конфигурацию WCF** пункт контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="ba7e7-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7e7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ba7e7-119">See Also</span></span>  
 [<span data-ttu-id="ba7e7-120">Редактор конфигурации (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="ba7e7-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="ba7e7-121">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="ba7e7-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="ba7e7-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba7e7-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
