---
title: Общие сведения о декоративных элементах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111183"
---
# <a name="adorners-overview"></a>Общие сведения о декоративных элементах

Adorners являются особым <xref:System.Windows.FrameworkElement>типом, используемым для предоставления визуальных сигналов для пользователя. Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.

## <a name="about-adorners"></a>Сведения о декоративных элементах

An <xref:System.Windows.Documents.Adorner> это <xref:System.Windows.FrameworkElement> обычай, который <xref:System.Windows.UIElement>связан с . Украшения отображаются <xref:System.Windows.Documents.AdornerLayer>в , который является рендеринга поверхности, которая всегда находится на вершине украшен элемент амортизированных элементов или коллекция украшенных элементов. Рендеринг оретора не зависит <xref:System.Windows.UIElement> от рендеринга того, к что должен быть привязан акрадер. Украшения, как правило, расположены по отношению к элементу, к которому он связан, используя стандартные 2D-координаты происхождения, расположенные в верхнем левом углу украшенного элемента.

Типичные сценарии использования декоративных элементов:

- Добавление функциональных ручек к элементу, <xref:System.Windows.UIElement> которое позволяет пользователю каким-то образом манипулировать элементом (изменять размер, поворачивать, перепозиционировать и т.д.).
- Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.
- Наложение визуальных <xref:System.Windows.UIElement>украшений на .
- Визуально маска или переопределить часть <xref:System.Windows.UIElement>или все .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет базовую среду для декоративных визуальных элементов. В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение. Ниже приведены примеры использования:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.|
|<xref:System.Windows.Documents.AdornerLayer>|Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.|
|<xref:System.Windows.Documents.AdornerDecorator>|Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.|

## <a name="implementing-a-custom-adorner"></a>Реализация пользовательского декоративного элемента

Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов. Пользовательский орелер создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.

> [!NOTE]
> Родитель является <xref:System.Windows.Documents.Adorner> то, <xref:System.Windows.Documents.AdornerLayer> что оказывает, а <xref:System.Windows.Documents.Adorner>не элемент украшают.

В следующем примере показан класс, который реализует простой декоративный элемент. Пример украшения просто украшает углы <xref:System.Windows.UIElement> с кругами.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
Следующее изображение показывает SimpleCircleAdorner <xref:System.Windows.Controls.TextBox>применяется к:

![Скриншот, на который изображен украшенный текстовый ящик.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Поведение отрисовки для декоративных элементов

Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор. Распространенным способом реализации поведения рендеринга <xref:System.Windows.UIElement.OnRender%2A> является переопределение метода и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для визуализации визуальных элементов, приведенных в качестве необходимости (как показано в приведенном выше примере).

> [!NOTE]
> Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей. Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.

## <a name="events-and-hit-testing"></a>События и проверка нажатия

Adorners получают входные события, <xref:System.Windows.FrameworkElement>как и любые другие.  Поскольку орелит всегда имеет более высокий z-порядок, чем элемент, который <xref:System.Windows.UIElement.Drop> <xref:System.Windows.UIElement.MouseMove>он украшает, ореонер получает входные события (например, или), которые могут быть предназначены для основного элемента, украшенного.  Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.

Для того, чтобы сквозной хит тестирования элементов <xref:System.Windows.UIElement.IsHitTestVisible%2A> под украшением, установить хит тест собственности **на ложные** на украшение.  Для получения дополнительной информации о тестировании хитов, [см.](../graphics-multimedia/hit-testing-in-the-visual-layer.md)

## <a name="adorning-a-single-uielement"></a>Декорирование одного элемента пользовательского интерфейса

Чтобы привязать орели <xref:System.Windows.UIElement>к конкретному, выполните следующие действия:

1. Вызов статический <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, <xref:System.Windows.Documents.AdornerLayer> чтобы <xref:System.Windows.UIElement> получить объект для украшения. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>идет вверх по визуальному дереву, начиная с указанного, <xref:System.Windows.UIElement>и возвращает первый слой украшения он находит. (Если слои декоративных элементов не найдены, метод возвращает значение 0.)

2. Вызов <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода, чтобы привязать <xref:System.Windows.UIElement>украшение к цели.

 Следующий пример связывает SimpleCircleAdorner (см. <xref:System.Windows.Controls.TextBox> выше) с именем *myTextBox:*

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.

## <a name="adorning-the-children-of-a-panel"></a>Декорирование дочерних объектов панели

Чтобы связать украшение с <xref:System.Windows.Controls.Panel>детьми, выполните следующие действия:

1. `static` Вызовите <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой украшения для элемента, дети которого должны быть украшены.

2. Перечислите через детей родительского элемента и <xref:System.Windows.Documents.AdornerLayer.Add%2A> вызовите метод, чтобы связать оредета к каждому элементу ребенка.

Следующий пример связывает SimpleCircleAdorner (см. выше) <xref:System.Windows.Controls.StackPanel> к детям имени *myStackPanel*:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Общие сведения о фигурах и базовых средствах рисования в WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Общие сведения об объектах Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Как-к темам](adorners-how-to-topics.md)
