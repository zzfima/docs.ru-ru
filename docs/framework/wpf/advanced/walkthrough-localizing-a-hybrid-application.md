---
title: Пример локализации гибридного приложения
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 010c8f75a1151f5606be5ffa63d60fca364bdb59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Пример локализации гибридного приложения
В этом пошаговом руководстве показано, как для локализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-на основе гибридного приложения.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] узла проекта.  
  
-   Добавление локализуемого содержимого.  
  
-   Включение локализации.  
  
-   Назначение идентификаторов ресурсов.  
  
-   Использование средства LocBaml для создания вспомогательной сборки.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [локализация пример гибридного приложения](http://go.microsoft.com/fwlink/?LinkID=160015).  
  
 Закончив, вы получите локализованное гибридное приложение.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-windows-forms-host-project"></a>Создание ведущего проекта Windows Forms  
 Первым шагом является создание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложения проекта и добавьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент содержимого, которое будет локализовано.  
  
#### <a name="to-create-the-host-project"></a>Создание ведущего проекта  
  
1.  Создание проекта приложения WPF с именем `LocalizingWpfInWf`. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> элемент с именем `SimpleControl` в проект.  
  
3.  Используйте <xref:System.Windows.Forms.Integration.ElementHost> управления, чтобы разместить `SimpleControl` элемент в форме. Дополнительные сведения см. в разделе [Пошаговое руководство: размещение трехмерных составного элемента управления WPF в Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).  
  
## <a name="adding-localizable-content"></a>Добавление локализуемого содержимого  
 Далее вы добавите [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] метки элемента управления и задайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое элемента в локализуемые строки.  
  
#### <a name="to-add-localizable-content"></a>Добавление локализуемого содержимого  
  
1.  В обозревателе решений дважды щелкните **на SimpleControl.xaml** откройте ее в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Задайте содержимое <xref:System.Windows.Controls.Button> управления, используя следующий код.  
  
     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  В обозревателе решений дважды щелкните **Form1** чтобы открыть его в конструкторе Windows Forms.  
  
4.  Откройте панель элементов и дважды щелкните **метка** для добавления в форму элемент управления label. Задайте для его свойства <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.  
  
5.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
     Оба `SimpleControl` элемент и элемент управления label отображать текст **«Hello»**.  
  
## <a name="enabling-localization"></a>Включение локализации  
 Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.  
  
#### <a name="to-enable-localization"></a>Включение локализации  
  
1.  В обозревателе решений дважды щелкните **Form1.cs** чтобы открыть его в конструкторе Windows Forms.  
  
2.  В окне «Свойства» задайте значение в формате **Localizable** свойства `true`.  
  
3.  В окне свойств установите для параметра **язык** свойства **испанский (Испания)**.  
  
4.  В конструкторе Windows Forms выберите элемент управления label.  
  
5.  В окне свойств установите для параметра <xref:System.Windows.Forms.Control.Text%2A> свойства `"Hola"`.  
  
     Новый файл ресурсов с именем Form1.es-ES.resx будет добавлен в проект.  
  
6.  В обозревателе решений щелкните правой кнопкой мыши **Form1.cs** и нажмите кнопку **Просмотр кода** чтобы открыть его в редакторе кода.  
  
7.  Скопируйте следующий код в `Form1` конструктор, предшествующий вызову `InitializeComponent`.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  В обозревателе решений щелкните правой кнопкой мыши **на LocalizingWpfInWf** и нажмите кнопку **выгрузить проект**.  
  
     Имя проекта помечается **(недоступно)**.  
  
9. Щелкните правой кнопкой мыши **на LocalizingWpfInWf**и нажмите кнопку **изменить LocalizingWpfInWf.csproj**.  
  
     Файл проекта откроется в редакторе кода.  
  
10. Скопируйте следующую строку в первую `PropertyGroup` в файле проекта.  
  
    ```xml  
    <UICulture>en-US</UICulture>   
    ```  
  
11. Сохраните файл проекта и закройте его.  
  
12. В обозревателе решений щелкните правой кнопкой мыши **на LocalizingWpfInWf** и нажмите кнопку **перезагрузить проект**.  
  
## <a name="assigning-resource-identifiers"></a>Назначение идентификаторов ресурсов  
 Вы можете сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов. Приложение MsBuild.exe автоматически устанавливает идентификаторы ресурсов при указании `updateuid` параметр.  
  
#### <a name="to-assign-resource-identifiers"></a>Назначение идентификаторов ресурсов  
  
1.  Из меню "Пуск" откройте командной строки Visual Studio.  
  
2.  Используйте приведенную ниже команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  В обозревателе решений дважды щелкните **на SimpleControl.xaml** чтобы открыть его в редакторе кода. Вы увидите, что `msbuild` добавлена команда `Uid` для всех элементов атрибута. Это облегчает локализацию через назначение идентификаторов ресурсов.  
  
     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  Нажмите клавишу F6 для построения решения.  
  
## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Использование LocBaml для создания вспомогательной сборки  
 Локализованное содержимое хранится в доступный только для ресурсов *вспомогательная сборка*. Средство командной строки LocBaml.exe для производства локализованной сборки для вашего [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого.  
  
#### <a name="to-produce-a-satellite-assembly"></a>Создание вспомогательной сборки  
  
1.  Скопируйте файл LocBaml.exe в папку проекта obj\Debug. Дополнительные сведения см. в разделе [локализации приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
2.  В окне командной строки используйте приведенную ниже команду для извлечения строк ресурсов во временный файл.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Откройте файл temp.csv с Visual Studio или другой текстовый редактор. Замените строку `"Hello"` на ее испанский перевод `"Hola"`.  
  
4.  Сохраните файл temp.csv.  
  
5.  Используйте приведенную ниже команду для создания локализованного файла ресурса.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     Файл LocalizingWpfInWf.g.es-ES.resources создается в папке obj\Debug.  
  
6.  Используйте приведенную ниже команду для создания локализованной вспомогательной сборки.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     Файл LocalizingWpfInWf.resources.dll создается в папке obj\Debug.  
  
7.  Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\Debug\es-ES. Замените существующий файл.  
  
8.  Запустите файл LocalizingWpfInWf.exe, который находится в папке проекта bin\Debug. Не выполняйте повторную сборку приложения, чтобы не перезаписать вспомогательную сборку.  
  
     В приложении выводятся локализованные строки вместо английских строк.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)  
 [Пошаговое руководство: Локализация форм Windows Forms](http://msdn.microsoft.com/library/9a96220d-a19b-4de0-9f48-01e5d82679e5)  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
