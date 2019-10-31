---
title: Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 8679181d720d9550cf60034a7cf1809b79198e83
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197900"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF
Чтобы обеспечить улучшенное взаимодействие с браузерами, можно использовать элементы управления Microsoft ActiveX в приложении на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В этом пошаговом руководстве показано, как можно разместить проигрыватель Microsoft Windows Media как элемент управления на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] странице.

 В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта.

- Создание элемента управления ActiveX.

- Размещение элемента управления ActiveX на странице WPF.

 После завершения этого пошагового руководства вы узнаете, как использовать элементы управления Microsoft ActiveX в приложении на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Необходимые компоненты
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Проигрыватель Microsoft Windows Media, установленный на компьютере, где установлена среда Visual Studio.

- Visual Studio 2010.

## <a name="creating-the-project"></a>Создание проекта

### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта

1. Создайте проект приложения WPF с именем `HostingAxInWpf`.

2. Добавьте в решение проект библиотеки элементов управления Windows Forms и присвойте проекту имя `WmpAxLib`.

3. В проекте Вмпакслиб добавьте ссылку на сборку проигрывателя Windows Media, которая называется WMP. dll.

4. Откройте **панель элементов**.

5. Щелкните правой кнопкой мыши **область элементов**и выберите пункт **выбрать элементы**.

6. Перейдите на вкладку **COM-компоненты** , выберите элемент управления **проигрывателя Windows Media** и нажмите кнопку **ОК**.

     Элемент управления проигрывателя Windows Media добавляется на **панель элементов**.

7. В обозреватель решений щелкните правой кнопкой мыши файл **UserControl1** и выберите команду **Переименовать**.

8. Измените имя на `WmpAxControl.vb` или `WmpAxControl.cs`в зависимости от языка.

9. Если появится запрос на переименование всех ссылок, нажмите кнопку **Да**.

## <a name="creating-the-activex-control"></a>Создание элемента управления ActiveX
Visual Studio автоматически создает класс-оболочку <xref:System.Windows.Forms.AxHost> для элемента управления Microsoft ActiveX, когда элемент управления добавляется в область конструктора. Следующая процедура создает управляемую сборку с именем Аксинтероп. Вмплиб. dll.

### <a name="to-create-the-activex-control"></a>Создание элемента управления ActiveX

1. Откройте Вмпаксконтрол. vb или WmpAxControl.cs в конструктор Windows Forms.

2. Из **панели элементов**добавьте элемент управления проигрывателя Windows Media в область конструктора.

3. В окно свойств задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления проигрывателя Windows Media значение <xref:System.Windows.Forms.DockStyle.Fill>.

4. Создайте проект библиотеки элементов управления Вмпакслиб.

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Размещение элемента управления ActiveX на странице WPF

### <a name="to-host-the-activex-control"></a>Размещение элемента управления ActiveX

1. В проекте Хостингаксинвпф добавьте ссылку на созданную сборку взаимодействия ActiveX.

     Эта сборка называется Аксинтероп. Вмплиб. dll и была добавлена в папку Debug проекта Вмпакслиб при импорте элемента управления проигрывателя Windows Media.

2. Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.

3. Добавьте ссылку на сборку [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], которая называется System. Windows. Forms. dll.

4. Откройте файл MainWindow. XAML в конструкторе WPF.

5. Назовите `grid1`элемент <xref:System.Windows.Controls.Grid>.

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. В представление конструирования или представлении XAML выберите элемент <xref:System.Windows.Window>.

7. В окно свойств перейдите на вкладку **события** .

8. Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.

9. Вставьте следующий код, обрабатывающий событие <xref:System.Windows.FrameworkElement.Loaded>.

     Этот код создает экземпляр элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> и добавляет экземпляр элемента управления `AxWindowsMediaPlayer` в качестве дочернего.

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
