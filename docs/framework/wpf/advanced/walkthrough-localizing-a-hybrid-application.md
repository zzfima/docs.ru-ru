---
title: "Пример локализации гибридного приложения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "гибридные приложения [взаимодействие с WPF]"
  - "локализация [взаимодействие с WPF]"
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Пример локализации гибридного приложения
В данном руководстве показано, как локализовать элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в гибридном приложении, основанном на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание ведущего проекта [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Добавление локализуемого содержимого.  
  
-   Включение локализации.  
  
-   Назначение идентификаторов ресурса.  
  
-   Использовать средства LocBaml для создания вспомогательных сборок.  
  
 Полный пример кода для задач, приведенных в этом руководстве, см. в разделе [Пример локализации гибридного приложения](http://go.microsoft.com/fwlink/?LinkID=160015).  
  
 Закончив, вы получите локализованное гибридное приложение.  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Создание ведущего проекта Windows Forms  
 Первым шагом является создание проекта приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и добавление элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с содержимым, которое будет локализовано.  
  
#### Для создания ведущего проекта  
  
1.  Создайте проект приложения WPF с именем `LocalizingWpfInWf`.  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Добавьте элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>, вызванный `SimpleControl`, к проекту.  
  
3.  Используйте элемент управления <xref:System.Windows.Forms.Integration.ElementHost> для размещения элемента `SimpleControl` на форме.  Дополнительные сведения см. в разделе [Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).  
  
## Добавление локализуемого содержимого  
 Далее, добавьте элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Label и установите содержимое для элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в значение локализуемой строки.  
  
#### Чтобы добавить локализуемое содержимое  
  
1.  В обозревателе решений дважды щелкните **SimpleControl.XAML**, чтобы открыть его в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Установите содержимое элемента управления <xref:System.Windows.Controls.Button> с помощью следующего кода.  
  
     [!code-xml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  В обозревателе решений дважды щелкните **Form1**, чтобы открыть его в конструкторе Windows Forms.  
  
4.  Откройте Панель элементов и дважды щелкните значок **Label**, чтобы добавить в форму элемент управления Label.  Задайте его свойству <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.  
  
5.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
     Элемент `SimpleControl` и элемент управления Label отобразят текст **"Hello"**.  
  
## Включение локализации  
 Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.  
  
#### Чтобы включить локализацию  
  
1.  В Solution Explorer щелкните дважды по **Form1.cs**, чтобы открыть его в конструкторе Windows Forms.  
  
2.  В окне свойств задайте свойству формы **Localizable** значение `true`.  
  
3.  В окне свойств задайте свойству**Language** значение **Spanish \(Spain\)**.  
  
4.  В конструкторе Windows Forms выберите элемент управления label.  
  
5.  В окне Properties установите значение <xref:System.Windows.Forms.Control.Text%2A> характеристика `"Hola"`.  
  
     Новый файл ресурсов с именем Form1.es\-ES.resx добавляется в проект.  
  
6.  В обозревателе решений щелкните правой кнопкой мыши на **Form1.cs** и нажмите кнопку **Просмотреть код**, чтобы открыть его в редакторе кода.  
  
7.  Скопируйте следующий код в конструктор `Form1`, предшествующий вызову `InitializeComponent`.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  В обозревателе решений щелкните правой кнопкой мыши на **LocalizingWpfInWf** и нажмите кнопку **Выгрузить проект**.  
  
     Имя проекта помечается **\(недоступно\)**.  
  
9. Щелкните правой кнопкой мыши на **LocalizingWpfInWf** и выберите команду **Изменить LocalizingWpfInWf.csproj**.  
  
     Файл проекта открывается в редакторе кода.  
  
10. Скопируйте следующую строку в первую `PropertyGroup` в файле проекта.  
  
    ```  
    <UICulture>en-US</UICulture>   
    ```  
  
11. Сохраните файл проекта и закройте его.  
  
12. В Solution Explorer правой кнопкой мыши щелкните по **LocalizingWpfInWf** и щелкните по **перегрузить проект**.  
  
## Назначение идентификаторов ресурса  
 Можно сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов.  Приложение MsBuild.exe автоматически устанавливает идентификаторы ресурсов при указании параметра `updateuid`.  
  
#### Чтобы назначить идентификаторы ресурса  
  
1.  Из меню Пуск откройте командную строку [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
2.  Используйте следующую команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  В обозревателе решений дважды щелкните на **SimpleControl.XAML**, чтобы открыть его в редакторе кода.  Вы увидите, что команда `msbuild` добавила атрибут `Uid` ко всем элементам.  Это облегчает локализацию через назначения идентификаторов ресурсов.  
  
     [!code-xml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  Нажать клавишу F6 для построения решения.  
  
## Использование LocBaml для производства вспомогательных сборок  
 Локализованное содержимое хранится только во *вспомогательной сборке* ресурсов.  Используйте средство командной строки LocBaml.exe для производства локализованной сборки для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
#### Для создания вспомогательной сборки  
  
1.  Скопируйте LocBaml.exe в каталог проекта obj\\Debug.  Дополнительные сведения см. в разделе [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
2.  В окне командной строки используйте следующую команду для извлечения строк ресурса во временный файл.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Откройте файл temp.csv с [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] или другим текстовым редактором.  Замените строку `"Hello"` на ее испанский перевод, `"Hola"`.  
  
4.  Сохраните файл temp.csv.  
  
5.  Используйте следующую команду для создания локализованного файла ресурса.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     Файл LocalizingWpfInWf.g.es ES.resources создается в папке obj\\Debug.  
  
6.  Используйте следующую команду для построения локализованной вспомогательной сборки.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     Файл LocalizingWpfInWf.resources.dll создается в папке obj\\Debug.  
  
7.  Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\\Debug\\es\-ES.  Замените существующий файл.  
  
8.  Запустите LocalizingWpfInWf.exe, который находится в папке проекта bin\\Debug.  Не перестраивайте приложение или вспомогательную сборку во время перезаписи.  
  
     Приложение показывает локализованные строки вместо английских строк.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)