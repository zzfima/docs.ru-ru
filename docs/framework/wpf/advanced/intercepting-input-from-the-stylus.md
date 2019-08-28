---
title: Перехват ввода, осуществляемого пером
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 2547c0aa2f3a14080868c2760fa8999eb99d3d16
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046332"
---
# <a name="intercepting-input-from-the-stylus"></a>Перехват ввода, осуществляемого пером
Архитектура предоставляет механизм для реализации низкоуровневого <xref:System.Windows.Input.Stylus> управления входными данными и создания объектов цифровых рукописных данных <xref:System.Windows.Ink.Stroke>. <xref:System.Windows.Input.StylusPlugIns> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Класс предоставляет механизм для реализации пользовательского поведения и применения его к потоку данных, поступающих от устройства пера, для достижения оптимальной производительности.  
  
 В этом разделе содержатся следующие подразделы:  
  
- [Архитектура](#Architecture)  
  
- [Реализация подключаемых модулей пера](#ImplementingStylusPlugins)  
  
- [Добавление подключаемого модуля в InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Заключение](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Архитектура  
 — Это эволюция интерфейсов API [стилусинпут](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) , описанных в статье [доступ к вводу с помощью пера и управление ими](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)в [пакете Microsoft Windows XP Tablet PC Edition Software Development Kit 1,7.](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409) <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>  
  
 Каждый <xref:System.Windows.UIElement> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>имеет свойство,равное.<xref:System.Windows.UIElement.StylusPlugIns%2A> Можно добавить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> к <xref:System.Windows.UIElement.StylusPlugIns%2A> свойству элемента, чтобы управлять <xref:System.Windows.Input.StylusPoint> данными по мере их создания. <xref:System.Windows.Input.StylusPoint>данные состоят из всех свойств, поддерживаемых системным дигитайзером, включая <xref:System.Windows.Input.StylusPoint.X%2A> <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> данные точек и <xref:System.Windows.Input.StylusPoint.Y%2A> , а также данные.  
  
 Объекты вставляются непосредственно в поток данных, поступающих <xref:System.Windows.Input.Stylus> от устройства, при добавлении в <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> свойство. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Порядок, в котором подключаемые модули добавляются в <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекцию, определяет порядок, в котором они будут принимать <xref:System.Windows.Input.StylusPoint> данные. Например, если добавить подключаемый модуль фильтра, который будет ограничивать входные данные в определенный регион, а затем добавить подключаемый модуль, который распознает жесты по мере их написания, подключаемый модуль, который распознает жесты, получит <xref:System.Windows.Input.StylusPoint> отфильтрованные данные.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Реализация подключаемых модулей пера  
 Чтобы реализовать подключаемый модуль, создайте класс, производный от <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Этот класс применяется к потоку данных в том виде, в котором <xref:System.Windows.Input.Stylus>они поступают из. В этом классе можно изменить значения <xref:System.Windows.Input.StylusPoint> данных.  
  
> [!CAUTION]
> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Если вызывается или вызывается исключение, приложение будет закрыто. Следует тщательно протестировать элементы управления, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> использующие, и использовать элемент управления только в том случае <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> , если вы уверены, что не создаст исключение.  
  
 В следующем примере показан подключаемый модуль, который ограничивают ввод с помощью <xref:System.Windows.Input.StylusPoint.X%2A> пера, изменяя <xref:System.Windows.Input.StylusPoint.Y%2A> значения и в <xref:System.Windows.Input.StylusPoint> данных, поступающих от <xref:System.Windows.Input.Stylus> устройства.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Добавление подключаемого модуля в InkCanvas  
 Самый простой способ использовать пользовательский подключаемый модуль — реализовать класс, производный от InkCanvas, и добавить его в <xref:System.Windows.UIElement.StylusPlugIns%2A> свойство.  
  
 В следующем примере демонстрируется пользовательская <xref:System.Windows.Controls.InkCanvas> , которая фильтрует рукописные данные.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Если добавить `FilterInkCanvas` в приложение и запустить его, вы заметите, что рукописный ввод не ограничен регионом, пока пользователь не завершит штрих. Это обусловлено <xref:System.Windows.Controls.InkCanvas> тем, что <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> имеет <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> свойство, которое является и уже является членом <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекции. Пользователь <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> , добавленный <xref:System.Windows.UIElement.StylusPlugIns%2A> в коллекцию, получает <xref:System.Windows.Input.StylusPoint> данные после <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> получения данных. В результате <xref:System.Windows.Input.StylusPoint> данные не будут фильтроваться до тех пор, пока пользователь не отрывает перо для завершения штриха. Чтобы отфильтровать рукописные данные по мере их рисования, необходимо вставить `FilterPlugin` <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>перед.  
  
 В следующем C# коде показан пользовательский <xref:System.Windows.Controls.InkCanvas> объект, который фильтрует рукописные данные по мере их прорисовки.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Заключение  
 Создав собственные <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> классы и вставляя их в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> коллекции, можно значительно улучшить поведение рукописного ввода. У вас есть доступ к <xref:System.Windows.Input.StylusPoint> данным по мере их создания, что дает возможность <xref:System.Windows.Input.Stylus> настраивать входные данные. Так как у вас есть такой низкоуровневый доступ <xref:System.Windows.Input.StylusPoint> к данным, вы можете реализовать сбор и отрисовку рукописного ввода с оптимальной производительностью приложения.  
  
## <a name="see-also"></a>См. также

- [Дополнительная обработка рукописных фрагментов](advanced-ink-handling.md)
- [Доступ к вводу с помощью пера и управление им](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
