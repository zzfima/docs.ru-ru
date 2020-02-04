---
title: Составной узел трехмерного элемента управления WPF в Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794211"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a>Пошаговое руководство. размещение составного трехмерного элемента управления WPF в Windows Forms

В этом пошаговом руководстве показано, как можно создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составной элемент управления и разместить его в Windows Forms элементах управления и формах с помощью элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.

В этом пошаговом руководстве будет реализована [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>, содержащая два дочерних элемента управления. <xref:System.Windows.Controls.UserControl> отображает трехмерный (трехмерный) конус. Отрисовка трехмерных объектов гораздо проще с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], чем с помощью Windows Forms. Поэтому имеет смысл разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> класса для создания трехмерной графики в Windows Forms.

В данном пошаговом руководстве представлены следующие задачи.

- Создание <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- Создание проекта Windows Forms узла.

- Размещение <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Prerequisites

Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Создание пользовательского элемента управления

1. Создайте проект **библиотеки пользовательских элементов управления WPF** с именем `HostingWpfUserControlInWf`.

2. Откройте UserControl1. XAML в конструкторе WPF.

3. Замените созданный код следующим кодом:

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Этот код определяет <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>, содержащий два дочерних элемента управления. Первый дочерний элемент управления является <xref:System.Windows.Controls.Label?displayProperty=nameWithType> элементом управления; второй — элемент управления <xref:System.Windows.Controls.Viewport3D>, отображающий трехмерную конус.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Создание ведущего проекта

1. Добавьте в решение проект **Windows Formsного приложения (.NET Framework)** с именем `WpfUserControlHost`.

2. В **Обозреватель решений**добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.

3. Добавьте ссылки на следующие сборки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. Добавьте ссылку на проект `HostingWpfUserControlInWf`.

5. В обозреватель решений установите проект `WpfUserControlHost` в качестве запускаемого проекта.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Размещение пользовательского элемента управления

1. В конструктор Windows Forms откройте форму Form1.

2. В окно свойств щелкните **события**, а затем дважды щелкните событие <xref:System.Windows.Forms.Form.Load>, чтобы создать обработчик событий.

     Редактор кода открывает только что созданный обработчик событий `Form1_Load`.

3. Замените код в Form1.cs на следующий код.

     Обработчик событий `Form1_Load` создает экземпляр `UserControl1` и добавляет Итто коллекцию дочерних элементов управления <xref:System.Windows.Forms.Integration.ElementHost>. Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> добавляется в коллекцию формы дочерних элементов управления.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Размещение составного элемента управления WPF в Windows Forms примере](https://go.microsoft.com/fwlink/?LinkID=160001)
