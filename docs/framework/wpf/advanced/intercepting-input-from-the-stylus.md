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
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181921"
---
# <a name="intercepting-input-from-the-stylus"></a>Перехват ввода, осуществляемого пером
Архитектура <xref:System.Windows.Input.StylusPlugIns> обеспечивает механизм реализации низкоуровневого контроля за <xref:System.Windows.Input.Stylus> ввозами и созданием цифровых чернил. <xref:System.Windows.Ink.Stroke> Класс <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> предоставляет механизм для реализации пользовательского поведения и применения его к потоку данных, поступающих от устройства стилуса для оптимальной производительности.  
  
 В этом разделе содержатся следующие подразделы:  
  
- [Архитектура](#Architecture)  
  
- [Реализация Stylus Plug-ins](#ImplementingStylusPlugins)  
  
- [Добавление подключаемого к InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Заключение](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 Это <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> эволюция [AIS StylusInput,](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) описанные в [доступе и манипулировании ввода пера](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10)).  
  
 Каждый из них <xref:System.Windows.UIElement> имеет свойство, <xref:System.Windows.UIElement.StylusPlugIns%2A> которое является <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Можно добавить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> свойство элемента <xref:System.Windows.UIElement.StylusPlugIns%2A> для <xref:System.Windows.Input.StylusPoint> управления данными по мере их посвябчиния. <xref:System.Windows.Input.StylusPoint>данные состоят из всех свойств, поддерживаемых <xref:System.Windows.Input.StylusPoint.X%2A> системным дигитайзером, включая данные и <xref:System.Windows.Input.StylusPoint.Y%2A> точечные <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> данные, а также данные.  
  
 Ваши <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> объекты вставляются непосредственно в поток <xref:System.Windows.Input.Stylus> данных, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> поступающих <xref:System.Windows.UIElement.StylusPlugIns%2A> с устройства при добавлении в свойство. Порядок добавления плагинов в <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекцию диктует порядок, в котором они будут получать <xref:System.Windows.Input.StylusPoint> данные. Например, если вы добавите плагин фильтра, ограничивающий вход ные данные в определенном регионе, а затем добавите плагин, который распознает жесты по мере их написания, плагин, распознавающим жесты, получит отфильтрованные <xref:System.Windows.Input.StylusPoint> данные.  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a>Реализация Stylus Plug-ins  
 Для реализации плагина, получить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>класс из . Этот класс применяется o поток данных, <xref:System.Windows.Input.Stylus>как он поступает из . В этом классе можно изменить значения <xref:System.Windows.Input.StylusPoint> данных.  
  
> [!CAUTION]
> Если <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> выбрасывает или вызывает исключение, приложение закрывается. Вы должны тщательно проверить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> элементы управления, которые потребляют <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и использовать только элемент управления, если вы уверены, не будет бросать исключение.  
  
 В следующем примере показан плагин, ограничивающий вход стилуса <xref:System.Windows.Input.StylusPoint.X%2A> путем изменения <xref:System.Windows.Input.StylusPoint.Y%2A> <xref:System.Windows.Input.StylusPoint> и значений данных <xref:System.Windows.Input.Stylus> по мере их поступления с устройства.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Добавление подключаемого к InkCanvas  
 Самый простой способ использовать пользовательский плагин — реализовать класс, который происходит <xref:System.Windows.UIElement.StylusPlugIns%2A> от InkCanvas, и добавить его в свойство.  
  
 В следующем примере <xref:System.Windows.Controls.InkCanvas> демонстрируется обычай, который фильтрует чернила.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Если вы `FilterInkCanvas` добавите в приложение и запустите его, вы заметите, что чернила не ограничиваются областью до тех пор, пока пользователь не завершит ход. Это <xref:System.Windows.Controls.InkCanvas> потому, <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> что имеет свойство, которое является <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и уже является членом коллекции. <xref:System.Windows.UIElement.StylusPlugIns%2A> Пользователь, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> добавленный <xref:System.Windows.UIElement.StylusPlugIns%2A> в коллекцию, получает данные <xref:System.Windows.Input.StylusPoint> после <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> получения данных. В результате данные <xref:System.Windows.Input.StylusPoint> будут отфильтро: только после того, как пользователь не поднимет перо, чтобы закончить ход. Чтобы отфильтровать чернила по мере того, `FilterPlugin` как <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>пользователь рисует их, необходимо вставить перед .  
  
 Следующий код C's <xref:System.Windows.Controls.InkCanvas> демонстрирует обычай, который фильтрует чернила по мере их нарисованного.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Заключение  
 Путем выводить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ваши собственные типы <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> и вставлять их в собрания, вы можете значительно увеличить поведение ваших цифровых чернил. У вас есть <xref:System.Windows.Input.StylusPoint> доступ к данным по мере их создания, что дает вам возможность настроить входные данные. <xref:System.Windows.Input.Stylus> Поскольку у вас такой низкоуровневый доступ к <xref:System.Windows.Input.StylusPoint> данным, можно реализовать сбор и визуализацию чернил с оптимальной производительностью для вашего приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Дополнительная обработка рукописных данных](advanced-ink-handling.md)
- [Доступ и манипулирование ввозами пера](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
