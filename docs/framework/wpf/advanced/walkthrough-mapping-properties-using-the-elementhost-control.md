---
title: Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7d1cf353f7e6c4b87c13598e7e6029960cd0f715
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197814"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost

В этом пошаговом руководстве показано, как использовать свойство <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>, чтобы сопоставлять свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с соответствующими свойствами размещенного элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта.

- Определение нового сопоставления свойства.

- Удаление сопоставления свойства по умолчанию.

- Расширение сопоставления свойства по умолчанию.

Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [сопоставление свойств с помощью примера элемента управления ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).

По завершении вы сможете сопоставлять [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойства с соответствующими свойствами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещенного элемента.

## <a name="prerequisites"></a>Необходимые компоненты

Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio 2017

## <a name="creating-the-project"></a>Создание проекта

### <a name="to-create-the-project"></a>Создание проекта

1. Создайте проект **приложения Windows Forms** с именем `PropertyMappingWithElementHost`.

2. В **Обозреватель решений**добавьте ссылки на следующие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборки.

    - PresentationCore

    - PresentationFramework

    - WindowsBase

    - WindowsFormsIntegration

3. Скопируйте следующий код в начало файла кода `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. Откройте `Form1` в конструкторе Windows Forms. Дважды щелкните форму, чтобы добавить обработчик событий для события <xref:System.Windows.Forms.Form.Load>.

5. Вернитесь к конструктор Windows Forms и добавьте обработчик событий для <xref:System.Windows.Forms.Control.Resize> события формы. Дополнительные сведения см. в разделе [инструкции. Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

6. Объявите поле <xref:System.Windows.Forms.Integration.ElementHost> в классе `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>Определение новых сопоставлений свойств

Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> предоставляет несколько сопоставлений свойств по умолчанию. Новое сопоставление свойств добавляется путем вызова метода <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> для <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.

### <a name="to-define-new-property-mappings"></a>Определение новых сопоставлений свойств

1. Скопируйте следующий код в определение класса `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     Метод `AddMarginMapping` добавляет новое сопоставление для свойства <xref:System.Windows.Forms.Control.Margin%2A>.

     Метод `OnMarginChange` преобразует свойство <xref:System.Windows.Forms.Control.Margin%2A> в свойство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A>.

2. Скопируйте следующий код в определение класса `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     Метод `AddRegionMapping` добавляет новое сопоставление для свойства <xref:System.Windows.Forms.Control.Region%2A>.

     Метод `OnRegionChange` преобразует свойство <xref:System.Windows.Forms.Control.Region%2A> в свойство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A>.

     Метод `Form1_Resize` обрабатывает событие <xref:System.Windows.Forms.Control.Resize> формы и изменяет размер вырезанной области в соответствии с размещаемым элементом.

## <a name="removing-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию

Удалите сопоставление свойств по умолчанию, вызвав метод <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> для <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.

### <a name="to-remove-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию

- Скопируйте следующий код в определение класса `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     Метод `RemoveCursorMapping` удаляет сопоставление по умолчанию для свойства <xref:System.Windows.Forms.Control.Cursor%2A>.

## <a name="extending-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию

Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.

### <a name="to-extend-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию

- Скопируйте следующий код в определение класса `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     Метод `ExtendBackColorMapping` добавляет настраиваемый транслятор свойств к существующему сопоставлению свойств <xref:System.Windows.Forms.Control.BackColor%2A>.

     Метод `OnBackColorChange` присваивает конкретному изображению свойство <xref:System.Windows.Controls.Control.Background%2A> размещаемого элемента управления. Метод `OnBackColorChange` вызывается после применения сопоставления свойства по умолчанию.

## <a name="initialize-your-property-mappings"></a>Инициализация сопоставлений свойств

1. Скопируйте следующий код в определение класса `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     Метод `Form1_Load` обрабатывает событие <xref:System.Windows.Forms.Form.Load> и выполняет следующую инициализацию.

    - Создает элемент <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

    - Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.

    - Присваивает начальные значения сопоставленным свойствам.

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
