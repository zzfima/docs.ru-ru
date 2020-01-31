---
title: Реализация клиентского поставщика автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, client-side provider implementation
- client-side UI Automation provider, implementation
- provider implementation, UI Automation
ms.assetid: 3584c0a1-9cd0-4968-8b63-b06390890ef6
ms.openlocfilehash: ec56d9b9dd4e7582f41aae0089d7be6f2b611031
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789640"
---
# <a name="client-side-ui-automation-provider-implementation"></a>Реализация клиентского поставщика автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В операционных системах Майкрософт используются несколько разных [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] платформ, в том числе Win32, Windows Forms и [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] предоставляет клиентам сведения об элементах пользовательского интерфейса. Однако модель [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] сама по себе не имеет сведений о разных типах элементов управления, которые существуют в этих инфраструктурах, и методах, необходимых для извлечения из них информации. Эта задача оставляется объектам, называемым поставщиками. Поставщик извлекает информацию из определенного элемента управления и передает ее в модель [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], которая затем последовательно предоставляет эту информацию клиенту.  
  
 Поставщики могут существовать на стороне сервера или на стороне клиента. Поставщик на стороне сервера реализуется самим элементом управления. Элементы[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] реализуют поставщики, как и любые сторонние элементы управления, созданные в расчете на модель [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Однако более старые элементы управления, такие как в Win32 и Windows Forms, не поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]напрямую. Вместо этого они обслуживаются поставщиками, которые существуют в процессе клиента и получают сведения об элементах управления с помощью межпроцессного взаимодействия, например наблюдая за сообщениями, которыми обмениваются Windows и элементы управления. Такие поставщики на стороне клиента иногда называются прокси.  
  
 Windows Vista предоставляет поставщики для стандартных элементов управления Win32 и Windows Forms. Кроме того, резервный поставщик обеспечивает частичную [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] поддержку для любого элемента управления, который не обслуживается другим поставщиком или прокси на стороне сервера, но имеет реализацию Microsoft Active Accessibility. Все эти поставщики автоматически загружаются и доступны для клиентских приложений.  
  
 Дополнительные сведения о поддержке элементов управления Win32 и Windows Forms см. в разделе [Поддержка модели автоматизации пользовательского интерфейса для стандартных элементов управления](ui-automation-support-for-standard-controls.md).  
  
 Приложения также могут регистрировать другие поставщики на стороне клиента.  
  
<a name="Distributing_Client-Side_Providers"></a>   
## <a name="distributing-client-side-providers"></a>Распространение поставщиков на стороне клиента  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ожидает найти поставщиков на стороне клиента в сборке управляемого кода. Пространство имен в этой сборке должно иметь имя, совпадающее с именем сборки. Например, сборка с именем ContosoProxies.dll будет содержать пространство имен ContosoProxies. В этом пространстве имен создайте класс <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders> . В реализации статического поля <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders.ClientSideProviderDescriptionTable> создайте массив структур <xref:System.Windows.Automation.ClientSideProviderDescription> , описывающий поставщиков.  
  
<a name="Registering_and_Configuring_Client-Side_Providers"></a>   
## <a name="registering-and-configuring-client-side-providers"></a>Регистрация и настройка поставщиков на стороне клиента  
 Поставщики на стороне клиента в библиотеке динамической компоновки (DLL) загружаются путем вызова <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviderAssembly%2A>. Для использования этих поставщиков дальнейших действий от клиентского приложения не требуется.  
  
 Поставщики, реализованные в собственном коде клиента, регистрируются с помощью метода <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>. Этот метод в качестве аргумента принимает массив структур <xref:System.Windows.Automation.ClientSideProviderDescription> , каждая из которых задает следующие свойства:  
  
- функцию обратного вызова, которая создает объект поставщика;  
  
- имя класса элементов управления, которые будет обслуживать поставщик;  
  
- имя образа приложения (обычно полное имя исполняемого файла), который поставщик будет обслуживать;  
  
- флаги, которые определяют, как имя класса сопоставляются с классами окон, находящимися в целевом приложении.  
  
 Последние два параметра являются необязательными. Клиент может задавать имя образа целевого приложения, если хочет использовать разные поставщики для разных приложений. Например, клиент может использовать одного поставщика для элемента управления представления списка Win32 в известном приложении, которое поддерживает шаблон нескольких представлений, а другой — для аналогичного элемента управления в другом известном приложении, которое не имеет.  
  
## <a name="see-also"></a>См. также:

- [Создание поставщика автоматизации пользовательского интерфейса на стороне клиента](create-a-client-side-ui-automation-provider.md)
- [Реализация поставщиков автоматизации пользовательского интерфейса в приложении клиента](implement-ui-automation-providers-in-a-client-application.md)
