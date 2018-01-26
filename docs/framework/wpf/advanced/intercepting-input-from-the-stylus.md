---
title: "Перехват ввода, осуществляемого пером"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5fde62e2e1ab17b26c91051f68b7d4225450c60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="intercepting-input-from-the-stylus"></a>Перехват ввода, осуществляемого пером
<xref:System.Windows.Input.StylusPlugIns> Архитектура предоставляет механизм для реализации низкоуровневого управления <xref:System.Windows.Input.Stylus> входных данных и создание рукописный <xref:System.Windows.Ink.Stroke> объектов. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Класс предоставляет механизм для реализации пользовательского поведения и применения его к потоку данных, поступающих от устройства пера, для обеспечения оптимальной производительности.  
  
 В этом разделе содержатся следующие подразделы:  
  
-   [Архитектура](#Architecture)  
  
-   [Реализация подключаемых модулей пера](#ImplementingStylusPlugins)  
  
-   [Добавление подключаемого модуля в InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Заключение](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Архитектура  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Развитие [потоке](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) API-интерфейсы, описанные в [получение и обработка ввода с помощью пера](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)в [XP Tablet PC Edition программным обеспечением Microsoft Windows Пакет средств разработки 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Каждый <xref:System.Windows.UIElement> имеет <xref:System.Windows.UIElement.StylusPlugIns%2A> свойства, которое является <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Можно добавить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> на элемент <xref:System.Windows.UIElement.StylusPlugIns%2A> свойства для управления <xref:System.Windows.Input.StylusPoint> данных, как оно создается. <xref:System.Windows.Input.StylusPoint>данные состоят из всех свойств, поддерживаемых системным дигитайзером, включая <xref:System.Windows.Input.StylusPoint.X%2A> и <xref:System.Windows.Input.StylusPoint.Y%2A> точки данных, а также <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> данных.  
  
 Ваш <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> объектов вставляются непосредственно в поток данных, поступающих от <xref:System.Windows.Input.Stylus> устройства при добавлении <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> для <xref:System.Windows.UIElement.StylusPlugIns%2A> свойства. Порядок добавления подключаемых модулей для <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекции определяет порядок, в котором они будут получать <xref:System.Windows.Input.StylusPoint> данных. Например, если добавить подключаемый модуль фильтра, ограничивающий входные данные для определенного региона, а затем добавить подключаемый модуль, который распознает жесты, они записываются, подключаемый модуль, который распознает жесты будет получать отфильтрованные <xref:System.Windows.Input.StylusPoint> данных.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Реализация подключаемых модулей пера  
 Чтобы реализовать подключаемый модуль, создайте класс, производный от <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Этот класс является o применяется к потоку данных, которые он поступает из <xref:System.Windows.Input.Stylus>. В этом классе можно изменить значения <xref:System.Windows.Input.StylusPoint> данных.  
  
> [!CAUTION]
>  Если <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> создает или вызывает исключение, приложение будет закрыто. Необходимо тщательно протестировать элементы управления, которые используют <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и использовать элемент управления, только если вы уверены, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> не будет вызвано исключение.  
  
 В следующем примере демонстрируется подключаемый модуль, который ограничивает входные данные пера путем изменения <xref:System.Windows.Input.StylusPoint.X%2A> и <xref:System.Windows.Input.StylusPoint.Y%2A> значения в <xref:System.Windows.Input.StylusPoint> данных, поступающих от <xref:System.Windows.Input.Stylus> устройства.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Добавление подключаемого модуля в InkCanvas  
 Самым простым способом использовать пользовательский подключаемый модуль является реализация класса, производного от InkCanvas и добавьте его в <xref:System.Windows.UIElement.StylusPlugIns%2A> свойство.  
  
 В следующем примере показано пользовательское <xref:System.Windows.Controls.InkCanvas> , фильтрует рукописные данные.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 При добавлении `FilterInkCanvas` к приложению и запустить его, вы заметите, что рукописные данные не ограничены областью, пока пользователь не завершит штрих. Это вызвано <xref:System.Windows.Controls.InkCanvas> имеет <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> свойство, которое является <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и уже является членом <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекции. Пользовательский <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> добавляемые <xref:System.Windows.UIElement.StylusPlugIns%2A> Получает коллекцию <xref:System.Windows.Input.StylusPoint> данных после <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> получает данные. В результате <xref:System.Windows.Input.StylusPoint> данные не будут фильтроваться до после пользователь отрывает перо, чтобы завершить штриха. Для фильтрации рукописный ввод, рисуемых пользователем, необходимо вставить `FilterPlugin` перед <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Следующий код C# демонстрирует пользовательский <xref:System.Windows.Controls.InkCanvas> , фильтрует рукописный ввод его написания.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Заключение  
 Путем наследования своих собственных <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> классы и вставляя их в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> коллекции, можно значительно улучшить обработку вашего рукописного ввода. У вас есть доступ к <xref:System.Windows.Input.StylusPoint> данных по мере доступными, предоставляя возможность настройки <xref:System.Windows.Input.Stylus> ввода. Если у вас такого низкоуровневого доступа к <xref:System.Windows.Input.StylusPoint> данных, можно реализовать коллекцию рукописного ввода и Подготовка к просмотру с оптимальной производительностью приложения.  
  
## <a name="see-also"></a>См. также  
 [Дополнительная обработка рукописных фрагментов](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [Доступ и управление ввода с помощью пера](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
