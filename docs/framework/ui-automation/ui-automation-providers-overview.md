---
title: Общие сведения о поставщиках автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 417cc17986fa1481505a88d778dcaa747860efbe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447980"
---
# <a name="ui-automation-providers-overview"></a>Общие сведения о поставщиках автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 Поставщики автоматизации пользовательского интерфейса включают элементы управления для взаимодействия с клиентскими приложениями модели автоматизации пользовательского интерфейса. В целом каждый элемент управления или другой отдельный элемент в [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] представляется поставщиком. Поставщик предоставляет сведения об этом элементе и при необходимости реализует шаблоны элементов управления, которые позволяют клиентскому приложению взаимодействовать с этим элементом управления.  
  
 Клиентские приложения обычно не должны работать непосредственно с поставщиками. Большинство стандартных элементов управления в приложениях, использующих инфраструктуру [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]или [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , автоматически предоставляется в систему [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Приложения, реализующие пользовательские элементы управления, могут также реализовывать поставщики [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для этих элементов управления, и клиентским приложениям не требуется предпринимать дополнительные действия для получения доступа к ним.  
  
 В этом разделе приведены общие сведения о том, как разработчики элементов управления реализуют поставщики [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , в частности для элементов управления в окнах [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] .  
  
<a name="Types_of_Providers"></a>   
## <a name="types-of-providers"></a>Типы поставщиков  
 Поставщики автоматизации пользовательского интерфейса делятся на две категории: поставщики на стороне клиента и поставщики на стороне сервера.  
  
### <a name="client-side-providers"></a>Поставщики на стороне клиента  
 Поставщики на стороне клиента реализуются клиентами автоматизации пользовательского интерфейса для взаимодействия с приложением, которое не поддерживает или не полностью поддерживает [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Client-side providers usually communicate with the server across the process boundary by sending and receiving Windows messages.  
  
 Because UI Automation providers for controls in [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], Windows Forms, or [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applications are supplied as part of the operating system, client applications seldom have to implement their own providers, and this overview does not cover them further.  
  
### <a name="server-side-providers"></a>Поставщики на стороне сервера  
 Server-side providers are implemented by custom controls or by applications that are based on a UI framework other than [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], Windows Forms, or [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].  
  
 Поставщики на стороне сервера взаимодействуют с клиентскими приложениями через границу процесса, предоставляя интерфейсы для базовой системы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которая в свою очередь обслуживает запросы от клиентов.  
  
<a name="AutomationProviderConcepts"></a>   
## <a name="ui-automation-provider-concepts"></a>Основные понятия поставщиков автоматизации пользовательского интерфейса  
 В этом разделе содержится краткое описание некоторых ключевых понятий, которые необходимо знать для реализации поставщиков автоматизации пользовательского интерфейса.  
  
### <a name="elements"></a>Элементы  
 Элементы[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — это части [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , видимые клиентам автоматизации пользовательского интерфейса. В качестве примеров можно привести окна приложений, панели, кнопки, подсказки, списки и элементы списков.  
  
### <a name="navigation"></a>Навигация  
 Элементы[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляются клиентам в виде дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] создает это дерево путем перемещения от одного элемента к другому. Поставщики разрешают навигацию для всех элементов, каждый из которых может указывать на родительский элемент, одноуровневые элементы и дочерние элементы.  
  
 Дополнительные сведения о клиентском представлении дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
### <a name="views"></a>Представления  
 Клиент может видеть дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в трех различных представлениях, как показано в следующей таблице.  
  
|||  
|-|-|  
|Базовое представление|Содержит все элементы.|  
|Представление элемента управления|Содержит элементы, которые являются элементами управления.|  
|Представление содержимого|Содержит элементы, которые имеют содержимое.|  
  
 Дополнительные сведения о клиентских представлениях дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 Поставщик в своей реализации определяет элемент как элемент содержимого или элемент управления. Элементы управления могут быть или не быть также и элементами содержимого, но все элементы содержимого являются элементами управления.  
  
### <a name="frameworks"></a>Инфраструктуры  
 Инфраструктура — это компонент, который управляет дочерними элементами управления, проверкой попадания и визуализацией в области экрана. Например, окно [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] , которое часто называют HWND, может служить инфраструктурой, которая содержит несколько элементов [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , таких как меню, строка состояния и кнопки.  
  
 Контейнерные элементы управления[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] , такие как списки и представления в виде дерева, считаются инфраструктурами, так как они содержат собственный код для визуализации дочерних элементов и выполнения проверки попадания в них. Напротив, список [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] не является инфраструктурой, поскольку визуализация и проверка попадания обрабатываются содержащим его окном [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] .  
  
 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] в приложении может состоять из разных инфраструктур. For example, an HWND application window might contain Dynamic HTML (DHTML) which in turn contains a component such as a combo box in an HWND.  
  
### <a name="fragments"></a>Фрагменты  
 Фрагмент — это полное поддерево элементов из определенной инфраструктуры. Элемент на уровне корневого узла поддерева называется корнем фрагмента. У корня фрагмента отсутствует родительский элемент, но он размещается в другой инфраструктуре, обычно в окне [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] (HWND).  
  
### <a name="hosts"></a>Узлы  
 Корневой узел каждого фрагмента должен быть размещен в элементе, обычно в окне [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] (HWND). Исключением является рабочий стол, который не размещается ни в каком другом элементе. Узлом пользовательского элемента управления является HWND самого элемента управления, а не окно приложения или какое-либо другое окно, которое может содержать группы элементов управления верхнего уровня.  
  
 Узел фрагмента играет важную роль в предоставлении служб [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Он позволяет навигацию в корень фрагмента и предоставляет некоторые свойства по умолчанию, чтобы настраиваемому поставщику не требовалось реализовывать их.  
  
## <a name="see-also"></a>См. также

- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
