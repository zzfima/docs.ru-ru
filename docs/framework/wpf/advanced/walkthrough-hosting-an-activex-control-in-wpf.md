---
title: "Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления ActiveX [взаимодействие с WPF]"
  - "размещение элементов управления ActiveX"
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF
Для улучшенного взаимодействия с браузером можно использовать элементы управления [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В данном примере демонстрируется, как разместить [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] в качестве элемента управления на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание проекта.  
  
-   Создание элемента ActiveX.  
  
-   Размещение элемента управления ActiveX на странице WPF.  
  
 По окончании ознакомления пользователь будет знать, как использовать элементы управления [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] должен быть установлен на компьютере, на котором установлено приложение [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Создание проекта  
  
#### Чтобы создать и настроить проект  
  
1.  Создайте проект приложения WPF с именем `HostingAxInWpf`.  
  
2.  Добавьте проект библиотеки элементов управления Windows Forms в решение и назовите проект `WmpAxLib`.  
  
3.  В проекте WmpAxLib добавьте ссылку на сборку проигрывателя Windows Media с именем wmp.dll.  
  
4.  Откройте **Панель элементов**.  
  
5.  Щелкните правой кнопкой мыши **Панель элементов** и выберите команду **Выбрать элементы**.  
  
6.  На вкладке **Компоненты COM** установите флажок **Проигрыватель Windows Media** и нажмите кнопку **ОК**.  
  
     Элемент управления "Проигрыватель Windows Media" добавлен в **панель элементов**.  
  
7.  В обозревателе решений щелкните правой кнопкой мыши файл **UserControl1**, а затем нажмите **Переименовать**.  
  
8.  Измените имя на `WmpAxControl.vb` или `WmpAxControl.cs`, в зависимости от языка.  
  
9. Если появится запрос на переименование всех ссылок, то нажмите кнопку **Да**.  
  
## Создание элемента ActiveX.  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] автоматически создает класс\-оболочку <xref:System.Windows.Forms.AxHost> для элемента управления [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)], когда элемент управления добавляется в рабочую область конструирования.  Следующая процедура создает управляемую сборку с именем AxInterop.WMPLib.dll.  
  
#### Чтобы создать элемент управления ActiveX  
  
1.  Откройте файл WmpAxControl.vb или WmpAxControl.cs в конструкторе Windows Forms.  
  
2.  Перетащите элемент управления "Проигрыватель Windows Media" с **панели элементов** в рабочую область конструирования.  
  
3.  В окне свойств задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления "Проигрыватель Windows Media" значение <xref:System.Windows.Forms.DockStyle>.  
  
4.  Выполните построение проекта библиотеки элементов управления WmpAxLib.  
  
## Размещение элемента управления ActiveX на странице WPF  
  
#### Чтобы разместить элемент управления ActiveX  
  
1.  В проекте HostingAxInWpf добавьте ссылку на созданную сборку взаимодействия [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)].  
  
     Эта сборка с именем AxInterop.WMPLib.dll добавлена в папку отладки проекта WmpAxLib при импорте элемента управления "Проигрыватель Windows Media".  
  
2.  Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.  
  
3.  Добавьте ссылку на сборку [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], которая называется System.Windows.Forms.dll.  
  
4.  Откройте файл MainWindow.xaml в конструкторе WPF.  
  
5.  Присвойте элементу <xref:System.Windows.Controls.Grid> имя `grid1`.  
  
     [!code-xml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  В представлении конструирования или представлении XAML выберите элемент <xref:System.Windows.Window>.  
  
7.  В окне свойств перейдите на вкладку **События**.  
  
8.  Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.  
  
9. Вставьте следующий код для обработки события <xref:System.Windows.FrameworkElement.Loaded>.  
  
     В этом коде создается экземпляр элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> и экземпляр `AxWindowsMediaPlayer` добавляется в качестве дочернего элемента управления.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Нажмите клавишу F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)