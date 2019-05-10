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
ms.openlocfilehash: 5b9af742558cd1a672c739040aef9e80dcaaabe5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652201"
---
# <a name="ui-automation-and-screen-scaling"></a>Модель автоматизации пользовательского интерфейса и масштабирование экрана
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] предоставляет пользователям возможность изменять параметр [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)] таким образом, чтобы большинство элементов [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] на экране отображалось большего размера. Хотя эта возможность уже давно была доступна в [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)], в предыдущих версиях масштабирование должно было реализовываться в приложениях. В [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)]диспетчер окон рабочего стола выполняет масштабирование по умолчанию для всех приложений, которые не обрабатывают собственное масштабирование. Клиентские приложения модели автоматизации пользовательского интерфейса должны учитывать эту функцию.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Масштабирование в Windows Vista  
 Параметр [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] по умолчанию имеет значение 96. Это означает, что ширина или высота в 1 номинальный дюйм занимает 96 пикселей. Точный размер "дюйма" зависит от размера и физического разрешения монитора. Например, на мониторе шириной в 12 дюймов при горизонтальном разрешении в 1280 пикселей горизонтальная линия в 96 пикселей имеет протяженность около 9/10 дюйма.  
  
 Изменение параметра [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] не эквивалентно изменению разрешения экрана. При масштабировании [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] количество физических пикселей на экране не меняется. Однако масштабирование применяется к размеру и расположению элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Это масштабирование может автоматически выполняться диспетчером окон рабочего стола для рабочего стола и для приложений, в которых не указан явный запрет на масштабирование.  
  
 В сущности, когда пользователь задает коэффициент масштабирования 120 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], вертикальный или горизонтальный дюйм на экране становится больше на 25 процентов. Все измерения масштабируются согласованно. Смещение окна приложения от верхнего и левого краев экрана увеличивается на 25 процентов. Если масштабирование приложения включено и приложение не поддерживает [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], размер окна увеличивается в той же пропорции, наряду со смещениями и размерами всех элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , которые в нем содержатся.  
  
> [!NOTE]
>  По умолчанию DWM не выполняет масштабирование для приложений, не поддерживающих[!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], когда пользователь устанавливает для [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] значение 120, но выполняет его, если для [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] задано пользовательское значение 144 или выше. Тем не менее пользователь может переопределить поведение по умолчанию.  
  
 Масштабирование экрана создает новые проблемы для приложений, которые каким-либо образом связаны с экранными координатами. Теперь экран содержит две системы координат: физическую и логическую. Физические координаты точки являются фактическим смещением в пикселях от верхнего левого угла начала координат. Логические координаты — это смещения, какими они были бы, если бы сами пиксели масштабировались.  
  
 Предположим, вы разрабатываете диалоговое окно с кнопкой, имеющей координаты (100, 48). Когда это диалоговое окно отображается при разрешении по умолчанию в 96 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], кнопка располагается в точке с физическими координатами (100, 48). При разрешении 120 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]она располагается в точке с физическими координатами (125, 60). Однако логические координаты одинаковы в любой [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] параметр: (100, 48).  
  
 Логические координаты важны, так как они делают поведение операционной системы и приложений последовательным вне зависимости от настройки [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] . Например, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> обычно возвращает логические координаты. Если навести курсор на элемент в диалоговом окне, возвращаются одни и те же координаты независимо от значения [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] . Если нарисовать элемент управления в точке (100, 100), он рисуется согласно этим логическим координатам и будет занимать одну и ту же относительную позицию при любом значении [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] .  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>Масштабирование в клиентах автоматизации пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [!INCLUDE[TLA#tla_api](../../../includes/tlasharptla-api-md.md)] не использует логические координаты. Следующие методы и свойства либо возвращают физические координаты, либо принимают их в качестве параметров.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 По умолчанию клиентское приложение модели автоматизации пользовательского интерфейса, работающее в среде с разрешением, отличным от 96- [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] , не сможет получать правильные результаты из этих методов и свойств. Например, поскольку положение курсора определяется в логических координатах, клиент не может просто передать эти координаты в метод <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> , чтобы получить элемент, находящийся под курсором. Кроме того, такое приложение не сможет правильно разместить окна за пределами клиентской области.  
  
 Решение состоит из двух частей.  
  
1. Во-первых, включите в клиентском приложении поддержку [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]. Для этого вызовите функцию [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `SetProcessDPIAware` во время запуска. В управляемом коде следующее объявление сделает эту функцию доступной.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Эта функция упрощает весь процесс, поддерживающего определение dpi, это означает, что все окна, принадлежащие к процессу, являются немасштабируемыми. В [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), например, четыре окна, входящие в прямоугольник выделения находятся в физических координатах, полученных из модели автоматизации пользовательского интерфейса, а не в логических координатах. Если пример не поддерживающего определение dpi, выделение будет выполнено в логических координатах на рабочем столе, что привело бы к неверному размещению в среде 96 dpi.  
  
2. Чтобы получить координаты курсора, вызовите функцию [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `GetPhysicalCursorPos`. В следующем примере показано, как объявлять и использовать эту функцию.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
>  Не используйте <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Поведение этого свойства вне клиентских окон в масштабируемой среде не определено.  
  
 Если приложение выполняет прямое межпроцессное взаимодействие с приложениями без поддержки [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], то возможно придется выполнять преобразование между логическими и физическими координатами с помощью функций [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `PhysicalToLogicalPoint` и `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>См. также

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
