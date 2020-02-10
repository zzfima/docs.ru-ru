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
ms.openlocfilehash: 7629843730a82584e94448ceac1ea574906876c9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095142"
---
# <a name="intercepting-input-from-the-stylus"></a>Перехват ввода, осуществляемого пером
Архитектура <xref:System.Windows.Input.StylusPlugIns> предоставляет механизм для реализации низкоуровневого контроля над входом <xref:System.Windows.Input.Stylus> и создания цифровых рукописных <xref:System.Windows.Ink.Stroke> объектов. Класс <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> предоставляет механизм для реализации пользовательского поведения и применения его к потоку данных, поступающих от устройства пера, для достижения оптимальной производительности.  
  
 В этом разделе содержатся следующие подразделы:  
  
- [Архитектура](#Architecture)  
  
- [Реализация подключаемых модулей пера](#ImplementingStylusPlugins)  
  
- [Добавление подключаемого модуля в InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Заключение](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architecture  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> является развитием API-интерфейсов [стилусинпут](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) , описанных в статье [доступ к вводу с помощью пера и управление](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))им.  
  
 Каждый <xref:System.Windows.UIElement> имеет свойство <xref:System.Windows.UIElement.StylusPlugIns%2A>, которое является <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Можно добавить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в свойство <xref:System.Windows.UIElement.StylusPlugIns%2A> элемента, чтобы управлять данными <xref:System.Windows.Input.StylusPoint> при их создании. <xref:System.Windows.Input.StylusPoint> данные состоят из всех свойств, поддерживаемых системным дигитайзером, включая <xref:System.Windows.Input.StylusPoint.X%2A> и данные точки <xref:System.Windows.Input.StylusPoint.Y%2A>, а также данные <xref:System.Windows.Input.StylusPoint.PressureFactor%2A>.  
  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> объекты вставляются непосредственно в поток данных, поступающих от устройства <xref:System.Windows.Input.Stylus>, при добавлении <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в свойство <xref:System.Windows.UIElement.StylusPlugIns%2A>. Порядок, в котором подключаемые модули добавляются в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>, определяет порядок, в котором они будут принимать <xref:System.Windows.Input.StylusPoint> данные. Например, если добавить подключаемый модуль фильтра, который будет ограничивать входные данные в определенный регион, а затем добавить подключаемый модуль, распознающий жесты по мере их написания, подключаемый модуль, распознающий жесты, получит отфильтрованные <xref:System.Windows.Input.StylusPoint> данные.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Реализация подключаемых модулей пера  
 Чтобы реализовать подключаемый модуль, создайте класс, производный от <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Этот класс применяется к потоку данных в том виде, в каком он поступает из <xref:System.Windows.Input.Stylus>. В этом классе можно изменить значения <xref:System.Windows.Input.StylusPoint> данных.  
  
> [!CAUTION]
> Если <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> создает или вызывает исключение, приложение будет закрыто. Следует тщательно протестировать элементы управления, использующие <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и использовать элемент управления, только если вы уверены, что <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> не создаст исключение.  
  
 В следующем примере демонстрируется подключаемый модуль, который ограничивают ввод с помощью пера, изменяя <xref:System.Windows.Input.StylusPoint.X%2A> и <xref:System.Windows.Input.StylusPoint.Y%2A> значения в <xref:System.Windows.Input.StylusPoint> данных по мере их поступающих с устройства <xref:System.Windows.Input.Stylus>.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Добавление подключаемого модуля в InkCanvas  
 Самый простой способ использовать пользовательский подключаемый модуль — реализовать класс, производный от InkCanvas, и добавить его в свойство <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
 В следующем примере демонстрируется пользовательский <xref:System.Windows.Controls.InkCanvas>, фильтрующий рукописный ввод.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Если добавить `FilterInkCanvas` в приложение и запустить его, вы заметите, что рукописный ввод не ограничен регионом, пока пользователь не завершит штрих. Это связано с тем, что <xref:System.Windows.Controls.InkCanvas> имеет свойство <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>, которое является <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и уже является членом коллекции <xref:System.Windows.UIElement.StylusPlugIns%2A>. Пользовательские <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, добавленные в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>, получают <xref:System.Windows.Input.StylusPoint> данные после <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> получения данных. В результате данные <xref:System.Windows.Input.StylusPoint> не будут фильтроваться до тех пор, пока пользователь не отрывает перо для завершения штриха. Чтобы отфильтровать рукописные данные по мере их рисования, необходимо вставить `FilterPlugin` перед <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 В следующем C# коде демонстрируется пользовательский <xref:System.Windows.Controls.InkCanvas>, который фильтрует рукописные данные по мере их прорисовки.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Заключение  
 Создав собственные классы <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и вставляя их в коллекции <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, можно значительно улучшить поведение рукописного ввода. У вас есть доступ к <xref:System.Windows.Input.StylusPoint>ным данным при их создании, что дает возможность настроить <xref:System.Windows.Input.Stylus> входные данные. Так как у вас есть такой низкоуровневый доступ к данным <xref:System.Windows.Input.StylusPoint>, можно реализовать сбор и отрисовку рукописного ввода с оптимальной производительностью для приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Дополнительная обработка рукописных фрагментов](advanced-ink-handling.md)
- [Доступ к вводу с помощью пера и управление им](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
