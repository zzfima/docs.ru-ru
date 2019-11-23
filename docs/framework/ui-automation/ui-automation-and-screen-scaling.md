---
title: Модель автоматизации пользовательского интерфейса и масштабирование экрана
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: ceab7db1f9eeb47ec020e220ec702af8181855e2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442483"
---
# <a name="ui-automation-and-screen-scaling"></a>Модель автоматизации пользовательского интерфейса и масштабирование экрана
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
Starting with Windows Vista, Windows enables users to change the dots per inch (dpi) setting so that most user interface (UI) elements on the screen appear larger. Although this feature has long been available in Windows, in previous versions the scaling had to be implemented by applications. Starting with Windows Vista, the Desktop Window Manager performs default scaling for all applications that do not handle their own scaling. Клиентские приложения модели автоматизации пользовательского интерфейса должны учитывать эту функцию.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Масштабирование в Windows Vista  
 The default dpi setting is 96, which means that 96 pixels occupy a width or height of one notional inch. Точный размер "дюйма" зависит от размера и физического разрешения монитора. Например, на мониторе шириной в 12 дюймов при горизонтальном разрешении в 1280 пикселей горизонтальная линия в 96 пикселей имеет протяженность около 9/10 дюйма.  
  
 Changing the dpi setting is not the same as changing the screen resolution. With dpi scaling, the number of physical pixels on the screen remains the same. Однако масштабирование применяется к размеру и расположению элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Это масштабирование может автоматически выполняться диспетчером окон рабочего стола для рабочего стола и для приложений, в которых не указан явный запрет на масштабирование.  
  
 In effect, when the user sets the scale factor to 120 dpi, a vertical or horizontal inch on the screen becomes bigger by 25 percent. Все измерения масштабируются согласованно. Смещение окна приложения от верхнего и левого краев экрана увеличивается на 25 процентов. If application scaling is enabled and the application is not dpi-aware, the size of the window increases in the same proportion, along with the offsets and sizes of all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements it contains.  
  
> [!NOTE]
> By default, the DWM does not perform scaling for non-dpi-aware applications when the user sets the dpi to 120, but does perform it when the dpi is set to a custom value of 144 or higher. Тем не менее пользователь может переопределить поведение по умолчанию.  
  
 Масштабирование экрана создает новые проблемы для приложений, которые каким-либо образом связаны с экранными координатами. Теперь экран содержит две системы координат: физическую и логическую. Физические координаты точки являются фактическим смещением в пикселях от верхнего левого угла начала координат. Логические координаты — это смещения, какими они были бы, если бы сами пиксели масштабировались.  
  
 Предположим, вы разрабатываете диалоговое окно с кнопкой, имеющей координаты (100, 48). When this dialog box is displayed at the default 96 dpi, the button is located at physical coordinates of (100, 48). At 120 dpi, it is located at physical coordinates of (125, 60). But the logical coordinates are the same at any dpi setting: (100, 48).  
  
 Logical coordinates are important, because they make the behavior of the operating system and applications consistent regardless of the dpi setting. Например, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> обычно возвращает логические координаты. If you move the cursor over an element in a dialog box, the same coordinates are returned regardless of the dpi setting. If you draw a control at (100, 100), it is drawn to those logical coordinates, and will occupy the same relative position at any dpi setting.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>Масштабирование в клиентах автоматизации пользовательского интерфейса  
 The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API does not use logical coordinates. Следующие методы и свойства либо возвращают физические координаты, либо принимают их в качестве параметров.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 By default, a UI Automation client application running in a non-96- dpi environment will not be able to obtain correct results from these methods and properties. Например, поскольку положение курсора определяется в логических координатах, клиент не может просто передать эти координаты в метод <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> , чтобы получить элемент, находящийся под курсором. Кроме того, такое приложение не сможет правильно разместить окна за пределами клиентской области.  
  
 Решение состоит из двух частей.  
  
1. First, make the client application dpi-aware. Для этого вызовите функцию [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `SetProcessDPIAware` во время запуска. В управляемом коде следующее объявление сделает эту функцию доступной.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     This function makes the entire process dpi-aware, meaning that all windows that belong to the process are unscaled. In the [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), for instance, the four windows that make up the highlight rectangle are located at the physical coordinates obtained from UI Automation, not the logical coordinates. If the sample were not dpi-aware, the highlight would be drawn at the logical coordinates on the desktop, which would result in incorrect placement in a non-96- dpi environment.  
  
2. Чтобы получить координаты курсора, вызовите функцию [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `GetPhysicalCursorPos`. В следующем примере показано, как объявлять и использовать эту функцию.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> Не используйте <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Поведение этого свойства вне клиентских окон в масштабируемой среде не определено.  
  
 If your application performs direct cross-process communication with non- dpi-aware applications, you may have convert between logical and physical coordinates by using the [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] functions `PhysicalToLogicalPoint` and `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>См. также

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
