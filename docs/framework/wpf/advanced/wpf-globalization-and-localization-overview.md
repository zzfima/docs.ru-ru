---
title: "Общие сведения о глобализации и локализации WPF | Microsoft Docs"
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
  - "глобализация, сведения о глобализации"
  - "локализация, о локализации"
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Общие сведения о глобализации и локализации WPF
Если доступность продукта ограничена только одним языком, то таким образом ограничивается потенциальная база клиентов до некоторой части всего 6.5\-миллиардного мирового населения.  Чтобы созданные приложения были доступны мировой аудитории, для достижения большего количества клиентов одним из лучших и наиболее экономичных способов является экономически эффективная локализация продукта.  
  
 В этом обзоре даются вводные сведения по глобализации и локализации в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Глобализация — это проектирование и разработка приложений, которые выполняются в нескольких расположениях.  Например, глобализация поддерживает локализованные пользовательские интерфейсы и региональные данные для пользователей на различных языках.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет глобализованные функциональные возможности проектирования, включая автоматическую структуру, вспомогательные сборки, а также локализованные атрибуты комментарии.  
  
 Локализация — это перевод ресурсов приложения в локализованные версии для конкретных языков и региональных параметров, которые поддерживает приложение.  При локализации в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используются интерфейсы API из пространства имен <xref:System.Windows.Markup.Localizer>. Эти интерфейсы API поддерживают средство командной строки [LocBaml](http://go.microsoft.com/fwlink/?LinkID=160016).  Сведения о том, как построить и использовать LocBaml, см. в разделе [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Рекомендации по глобализации и локализации в WPF  
 Большую часть функциональных возможностей глобализации и локализации, встроенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], можно создать, следуя советам по проектированию пользовательского интерфейса и локализации, представленным в этом разделе.  
  
### Оптимальные методы разработки пользовательского интерфейса WPF  
 При разработке [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], основанном на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо учитывать следующие рекомендации:  
  
-   Создавайте элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; избегайте создания элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в коде.  При создании элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с использованием [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] пользовательский интерфейс предоставляется через встроенные API\-интерфейсы локализации.  
  
-   Избегайте использования абсолютного позиционирования и фиксированных размеров для размещения содержимого; вместо этого используйте относительное или автоматическое изменение размеров.  
  
    -   Необходимо использовать <xref:System.Windows.Window.SizeToContent%2A>; установки для параметров ширины и высоты должны сохраняться как `Auto`.  
  
    -   Не следует использовать <xref:System.Windows.Controls.Canvas> для размещения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
    -   Рекомендуется использовать <xref:System.Windows.Controls.Grid> и ее функциональную возможность общего изменения размера.  
  
-   Необходимо предусмотреть дополнительное пространство в границах, поскольку локализованный текст часто занимает больше места.  Дополнительное пространство позволит использовать выступающие символы, возможно присутствующие в конкретном языке.  
  
-   Чтобы не допустить усечение текста, необходимо включить параметр <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> объекта <xref:System.Windows.Controls.TextBlock>.  
  
-   Необходимо задать атрибут **xml:lang**.  Этот атрибут описывает язык и региональные параметры конкретного элемента и его дочерних элементов.  Значение этого свойства изменяет поведение некоторых функциональных возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Например, изменяется процесс переноса по слогам, проверки орфографии, подстановки чисел, формирования сложных скриптов и подмены шрифта.  См. в разделе [Глобализация для WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md) дополнительные сведения о настройке [Обработка xml:lang в XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md).  
  
-   Рекомендуется создавать настраиваемый составной шрифт, чтобы получить лучшее управление шрифтами, использующимися для разных языков.  По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует шрифт GlobalUserInterface.composite из папки Windows\\Fonts.  
  
-   При создании приложений навигации, которые могут быть локализованы в языке, использующем представление текста в формате справа налево, необходимо явно установить <xref:System.Windows.FlowDirection> каждой страницы, чтобы гарантировать, что страница не будет наследовать <xref:System.Windows.FlowDirection> от <xref:System.Windows.Navigation.NavigationWindow>.  
  
-   При создании автономных приложений навигации, размещенных вне браузера, требуется установить для параметра <xref:System.Windows.Application.StartupUri%2A> начального приложения значение <xref:System.Windows.Navigation.NavigationWindow> вместо страницы \(например, `<Application StartupUri="NavigationWindow.xaml">`\).  Такая конструкция позволяет изменять <xref:System.Windows.FlowDirection> окна и панели переходов.  Дополнительные сведения и пример см. в разделе [Пример Globalization Homepage](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
### Оптимальные методы локализации приложений WPF  
 При локализации приложений на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] необходимо учитывать следующие рекомендации по реализации.  
  
-   Используйте комментарии локализации для обеспечения дополнительного контекста для локализаторов.  
  
-   Используйте атрибуты локализации для управления локализацией вместо выборочного пропуска свойств <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> в элементах.  Дополнительные сведения см. в разделе [Атрибуты и комментарии локализации](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
-   Необходимо использовать команды **msbuild \/t:updateuid** и **\/t:checkuid** для добавления и проверки свойств <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> в коде [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Используйте свойства <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> для отслеживания изменений между разработкой и локализацией. Свойства<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> помогают локализовать новые изменения в разработке.  При добавлении свойств <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] вручную эта задача становится более трудоемкой и менее точной.  
  
    -   Не следует редактировать или изменять свойства <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> после начала локализации.  
  
    -   Не следует использовать повторяющиеся свойства <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> \(необходимо помнить этот совет при использовании команды копировать\-вставить\).  
  
    -   Необходимо задать расположение `UltimateResourceFallback` в AssemblyInfo.\*, чтобы указать соответствующий язык в качестве базового языка \(например, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`\).  
  
         Если потребуется включить базовый язык в основную сборку путем пропуска тега `<UICulture>` в файле проекта, необходимо установить расположение `UltimateResourceFallback` в качестве основной сборки вместо вспомогательной \(например, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`\).  
  
<a name="workflow_to_localize"></a>   
## Локализация приложения WPF  
 Существует несколько вариантов локализации приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Например, можно привязать локализованные ресурсы в приложении к файлу [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], хранить локализуемый текст в resx\-таблицах, или же указать локализатору использовать файлы [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  В этом разделе описывается рабочий процесс локализации, использующий BALM\-форму XAML, который предоставляет несколько преимуществ.  
  
-   Локализация может делаться после построения.  
  
-   Можно выполнить обновление до более новой версии BALM\-формы XAML с локализациями из старой версии BALM\-формы XAML, чтобы обеспечить возможность локализации в процессе разработки.  
  
-   Можно проверять элементы и семантику исходного источника во время компиляции, поскольку BALM\-форма XAML является скомпилированной формой [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
### Процесс построения локализации  
 При разработке приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] процесс построения локализации состоит в следующем:  
  
-   Разработчик создает и глобализует приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В файле проекта разработчик задает параметр `<UICulture>en-US</UICulture>`, чтобы при компиляции приложения создавалась независимая от языка основная сборка. Эта сборка имеет вспомогательный файл .resources.dll, содержащий все локализуемые ресурсы. При необходимости можно хранить базовый язык в основной сборке, поскольку [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] локализации поддерживают извлечение из основной сборки.  
  
-   При компиляции файла в построение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуется в BALM\-форму XAML.  Независимый от языка и региональных параметров файл `MyDialog.exe` и зависимый от языка и региональных параметров \(английских\) файл `MyDialog.resources.dll` выпущены для англоговорящего клиента.  
  
### Технология локализации  
 Процесс локализации начинается после сборки нелокализованного файла `MyDialog.resources.dll`.  Элементы и свойства [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в исходном коде [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] извлекаются из BALM\-формы XAML в пары "ключ\-значение" с помощью [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] из пространства имен <xref:System.Windows.Markup.Localizer>.  Локализаторы используют пары ключ\-значение для локализации приложения.  После завершения локализации можно создать новый файл .resource.dll из новых значений.  
  
 Ключи пар "ключ\-значение" — это значения `x:Uid`, которые помещаются разработчиком в исходный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Эти значения `x:Uid` позволяют [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] осуществлять отслеживание и слияние изменений, внесенных разработчиком и локализатором во время локализации.  Например, если разработчик изменяет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] после начала локализации, можно слить их с уже выполненной работой по локализации, так что теряется минимум работы по переводу.  
  
 На приведенном ниже рисунке показана типичный рабочий процесс локализации на основе BALM\-формы XAML.  Эта диаграмма предполагает, что разработчик пишет приложение на английском языке.  Разработчик создает и глобализует приложение WPF.  В файле проекта разработчик задает `<UICulture>en-US</UICulture>` таким образом, что при построении основная независимая от языка сборка получает созданный вспомогательной сборкой файл .resources.dll, содержащий все локализуемые ресурсы.  Кроме того, можно сохранить базовый язык в основной сборке, поскольку локализация WPF API\-интерфейсов поддерживает извлечение из основной сборки.  По завершении процесса построения XAML компилируется в BAML.  Независимый от языка и региональных параметров MyDialog.exe.resources.dll поставляется англоязычному пользователю.  
  
 ![Локализация рабочего процесса](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![Нелокализированный рабочий процесс](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
<a name="examples_of_localization"></a>   
## Примеры локализации WPF  
 В этом разделе приводятся примеры локализованных приложений, чтобы облегчить понимание процесса построения и локализации приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
#### Пример диалогового окна "Выполнить"  
 На следующем рисунке показан вывод демонстрационного диалогового окна **Выполнить**.  
  
 **Английский:**  
  
 ![Выполнение &#45; диалоговое окно](../../../../docs/framework/wpf/advanced/media/rundialogenglish.png "RunDialogEnglish")  
  
 **Немецкий:**  
  
 ![Немецкий вариант диалогового окна ''Выполнение''](../../../../docs/framework/wpf/advanced/media/rundialoggerman.png "RunDialogGerman")  
  
 **Построение глобального диалогового окна "Выполнить"**  
  
 В этом примере показано создание диалогового окна **Выполнить** при помощи [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Это диалоговое окно является эквивалентом диалогового окна **Выполнить**, доступного из меню "Пуск" [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)].  
  
 Некоторые замечания по созданию глобальных диалоговых окон:  
  
 **Automatic Layout**  
  
 *В Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 Предыдущее свойство Window автоматически изменяет размер окна в соответствии с размером содержимого.  Это свойство предотвращает обрезание содержимого окна, которое увеличивается в размере после локализации; кроме того, оно также удаляет лишнее пространство, если содержимое уменьшается в размерах после локализации.  
  
 `<Grid x:Uid="Grid_1">`  
  
 Свойства <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> необходимы для корректной работы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по выполнению локализации [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].  
  
 Они используются при выполнении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] локализации [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] для отслеживания изменений между разработкой и локализацией [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Свойства <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> позволяют выполнить слияние более новой версии [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] со старой локализацией [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Свойство <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> добавляется при запуске **msbuild \/t:updateuid RunDialog.csproj** в командной оболочке.  Это рекомендуемый способ добавления свойств <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>, потому что добавление их вручную обычно является более затратным по времени и менее точным..  Чтобы проверить корректность задания свойств <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>, можно запустить **msbuild \/t:checkuid RunDialog.csproj**.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] структурирован при помощи элемента управления <xref:System.Windows.Controls.Grid>, который помогает воспользоваться преимуществами автоматического макета в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Обратите внимание, что диалоговое окно разделено на три строки и пять столбцов.  Ни в одном из определений строк и столбцов не задан фиксированный размер; следовательно, элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], расположенные в каждой ячейке, могут адаптироваться к увеличению и уменьшению размеров во время локализации.  
  
 [!code-xml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Первые два столбца, в которых размещены метка **Открыть:** и поле со списком <xref:System.Windows.Controls.ComboBox>, занимают 10 процентов всей ширины [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 [!code-xml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Обратите внимание, что пример использует функциональную возможность общего изменения размера <xref:System.Windows.Controls.Grid>.  Последние три столбца используют это преимущество, размещаясь в одной группе <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>.  Во время ожидания имени свойства это позволит столбцам использовать один и тот же размер.  Поэтому когда "Browse…" локализуется в более длинную строку "Durchsuchen…", ширина всех кнопок увеличивается, и не возникает ситуация с маленькой кнопкой "ОК" и непропорционально большой кнопкой "Durchsuchen…".  
  
 **Xml:lang**  
  
 `Xml:lang="en-US"`  
  
 Обратите внимание, что [Обработка xml:lang в XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) помещается в корневом элементе [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Это свойство описывает язык и региональные параметры конкретного элемента и его потомков.  Это значение используется несколькими функциональными возможностями в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], поэтому во время локализации оно должно быть соответствующим образом изменено.  Это значение изменяется в зависимости от того, какой языковый словарь используется для расстановки переносов и проверки орфографии слов.  Оно также влияет на отображение цифр и на то, как система подмены шрифтов выбирает шрифт для использования.  Наконец, это свойство влияет на способ отображения чисел и на способ написания текста в сложных скриптах.  По умолчанию используется значение "en\-US".  
  
 **Building a Satellite Resource Assembly**  
  
 *В .csproj:*  
  
 `<UICulture>en-US</UICulture>`  
  
 Обратите внимание на добавление значения `UICulture`.  Когда оно установлено в допустимое значение <xref:System.Globalization.CultureInfo>, например "en\-US", построение проекта создаст вспомогательную сборку со всеми локализуемыми ресурсами.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 Не нужно локализовывать `RunIcon.JPG`, так как он должен быть одинаков для всех языков и региональных параметров.  Свойству `Localizable` присвоено значение `false`, таким образом этот элемент остается в независимой от языка основной сборке, а не переносится во вспомогательную сборку.  Для всех некомпилируемых ресурсов свойству `Localizable` по умолчанию присвоено значение `true`.  
  
 **Локализация диалогового окна "Выполнить"**  
  
 **Parse**  
  
 После того как приложение будет построено, первым шагом в локализации является разбор локализуемых ресурсов из вспомогательной сборки.  В процессе изучения данного раздела используется демонстрационный инструмент LocBaml, который можно найти в разделе [Пример LocBaml](http://go.microsoft.com/fwlink/?LinkID=160016).  Обратите внимание, что LocBaml ― только демонстрационный инструмент, предназначенный помочь начать работу по созданию инструмента локализации, встраиваемого в процесс локализации.  С помощью LocBaml выполните следующую команду для анализа: **LocBaml \/parse RunDialog.resources.dll \/out:**. В результате создается файл RunDialog.resources.dll.CSV.  
  
 **Localize**  
  
 Для редактирования этого файла можно воспользоваться любым CSV\-редактором, поддерживающим Unicode.  Исключите все записи с категорией локализации "Нет".  Должны остаться следующие записи:  
  
||||  
|-|-|-|  
|Ключ ресурса|Категория локализации|Значение|  
|Button\_1:System.Windows.Controls.Button.$Content|Кнопка|ОК|  
|Button\_2:System.Windows.Controls.Button.$Content|Кнопка|Отмена|  
|Button\_3:System.Windows.Controls.Button.$Content|Кнопка|Обзор...|  
|ComboBox\_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Текст|Введите имя программы, папки, документа или Интернет\-ресурса, и Windows откроет его.|  
|TextBlock\_2:System.Windows.Controls.TextBlock.$Content|Текст|Открыть:|  
|Window\_1:System.Windows.Window.Title|Заголовок|Запуск|  
  
 Для локализации приложений в немецком языке потребуются следующие переводы:  
  
||||  
|-|-|-|  
|Ключ ресурса|Категория локализации|Значение|  
|Button\_1:System.Windows.Controls.Button.$Content|Кнопка|ОК|  
|Button\_2:System.Windows.Controls.Button.$Content|Кнопка|Abbrechen|  
|Button\_3:System.Windows.Controls.Button.$Content|Кнопка|Durchsuchen…|  
|ComboBox\_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Текст|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetresource an.|  
|TextBlock\_2:System.Windows.Controls.TextBlock.$Content|Текст|Öffnen:|  
|Window\_1:System.Windows.Window.Title|Заголовок|Запуск|  
  
 **Generate**  
  
 Последний шаг локализации включает создание только что локализованной вспомогательной сборки.  Это может быть выполнено с помощью следующей команды LocBaml:  
  
 **LocBaml.exe \/generate RunDialog.resources.dll \/trans:RunDialog.resources.dll.CSV \/out: .  \/cul:de\-DE**  
  
 В немецком [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], если файл resources.dll размещен в папке de\-DE главной сборки, этот ресурс будет автоматически загружаться вместо ресурса из папки en\-US.  Если немецкая версия [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] отсутствует, то чтобы проверить это, установите тот язык и региональные параметры, которые используются в вашей [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] \(т.е.  ru\-RU\), и замените исходный файл resources.dll.  
  
 **Satellite Resource Loading**  
  
|MyDialog.exe|en\-US\\MyDialog.resources.dll|De\-DE\\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Код|Исходный английский BAML|Локализованный BAML|  
|Ресурсы, не зависящие от языка и региональных параметров|Другие ресурсы на английском языке|Другие ресурсы, локализованные для немецкого языка|  
  
 Платформа .NET framework автоматически выбирает вспомогательную сборку ресурсов для загрузки в зависимости от `Thread.CurrentThread.CurrentUICulture` приложения.  По умолчанию используется языка и региональных параметров операционной системы [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  Поэтому при использовании немецкой [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] загружается "de\-DE\\MyDialog.resources.dll", а при использовании английской [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] загружается "en\-US\\MyDialog.resources.dll".  Можно задать для приложения встроенный ресурс, указав NeutralResourcesLanguage в AssemblyInfo.\* проекта.  Например, если будет указано:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 то в случае недоступности de\-DE\\MyDialog.resources.dll и de\\MyDialog.resources.dll немецкой версией Windows будет использоваться en\-US\\MyDialog.resources.dll.  
  
### домашняя страница Microsoft Saudi Arabia  
 На следующем рисунке показаны английская и арабская начальные страницы.  Полный пример создания такой графики см. в разделе [Пример Globalization Homepage](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Английский:**  
  
 ![Английская страница](../../../../docs/framework/wpf/advanced/media/englishhomepage.png "EnglishHomepage")  
  
 **Арабский:**  
  
 ![Арабская страница](../../../../docs/framework/wpf/advanced/media/arabichomepage.png "ArabicHomepage")  
  
### Проектирование глобальной домашней страницы Microsoft  
 Данный макет веб\-узла Microsoft Saudi Arabia показывает функциональные возможности глобализации, предоставляемые для языков с порядком чтения справа\-налево \(RightToLeft\).  Такие языки, как иврит и арабский, имеют порядок чтения справа\-налево, поэтому макет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] часто надо располагать совершенно иначе, нежели в языках с порядком чтения слева\-направо, как например в английском языке.  Локализация языка с направлением письма слева\-направо в язык с направлением письма справа\-налево или наоборот может быть достаточно сложной.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] был разработан, чтобы значительно упростить подобные локализации.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Обратите внимание на свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> в <xref:System.Windows.Controls.Page>.  Изменение этого свойства на <xref:System.Windows.FlowDirection> приведет к изменению <xref:System.Windows.FrameworkElement.FlowDirection%2A> страницы <xref:System.Windows.Controls.Page> и всех ее дочерних элементов, поэтому макет этого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] зеркально отразится и примет вид, предназначенный для порядка чтения справа налево, как того и ожидает арабский пользователь.  Можно переопределить это наследуемое поведение, явно указав свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> в любом элементе.  Свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> доступно для любого элемента <xref:System.Windows.FrameworkElement> или элемента, связанного с документом, и имеет неявное значение <xref:System.Windows.FlowDirection>.  
  
 Обратите внимание, что даже фоновые градиентные кисти при изменении свойства <xref:System.Windows.FrameworkElement.FlowDirection%2A> корня изменяются соответствующим образом.  
  
 **FlowDirection\="LeftToRight"**  
  
 ![Направление потока слева&#45;направо](../../../../docs/framework/wpf/advanced/media/lefttoright.png "LeftToRight")  
  
 **FlowDirection\="RightToLeft"**  
  
 ![Направление потока справа&#45;налево](../../../../docs/framework/wpf/advanced/media/righttoleft.png "RightToLeft")  
  
 **Избегайте использования фиксированных размеров для панелей и элементов управления**  
  
 Обратите внимание, что на всей домашней странице Homepage.xaml, помимо фиксированной ширины и высоты, заданной для всего [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] вверху <xref:System.Windows.Controls.DockPanel>, отсутствуют какие\-либо другие фиксированные размеры.  Не следует использовать фиксированные размеры, чтобы предотвратить отсечение локализованного текста, который может быть больше, чем исходный текст.  Панели и элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будут автоматически изменяться в размерах в зависимости от находящегося в них содержимого.  Большинство элементов управления также имеют минимальные и максимальные размеры, которые можно задать для большего регулирования \(например,  MinWidth\= "20"\).  С помощью элемента управления <xref:System.Windows.Controls.Grid> также можно задать относительную ширину и высоту, используя символ "\*" \(например,  Width\= "0,25\*"\) или возможность совместного использования размера ячейки.  
  
 **Комментарии локализации**  
  
 Во многих случаях содержимое может быть неоднозначным и трудным для перевода.  Разработчик и проектировщик имеют возможность предоставить локализаторам дополнительный контекст и комментарии в комментариях локализации.  Например, в приведенных ниже комментариях локализации уточняется использование символа "&#124;".  
  
 [!code-xml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Этот комментарий становится связанным с полем TextBlock\_1, и в инструменте LocBaml \(см. [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)\) его можно увидеть в выходном .csv файле, в шестом столбце строки TextBlock\_1:  
  
|||||||  
|-|-|-|-|-|-|  
|Ключ ресурса|Категория|Для чтения|Изменяемый|Комментарий|Значение|  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Текст|TRUE|TRUE|Этот символ используется в качестве декоративного правила.|&#124;|  
  
 Комментарии могут быть помещены в содержимое или в свойство любого элемента посредством следующего синтаксиса:  
  
 [!code-xml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Атрибуты локализации**  
  
 Разработчику или менеджеру локализации часто бывает необходимо управлять тем, что локализаторы могут читать и изменять.  Например, может быть нежелательно, чтобы локализатор переводил название компании или юридическую формулировку.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеются атрибуты, позволяющие задать возможность чтения, возможность модификации, а также категорию содержимого или свойства элемента; эти атрибуты можно использовать в инструменте локализации для блокировки, скрытия или сортировки элементов.  Дополнительные сведения см. в разделе <xref:System.Windows.Localization.Attributes%2A>.  В данном примере инструмент LocBaml только выводит значения этих атрибутов.  Во всех элементах управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эти атрибуты имеют значения по умолчанию, но их можно переопределять.  Например, в следующем примере переопределяются атрибуты локализации по умолчанию для `TextBlock_1` и задается возможность чтения и невозможность изменения содержимого для локализаторов.  
  
 [!code-xml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 В дополнение к атрибутам, задающим возможность чтения и изменения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет перечисление общих категорий пользовательского интерфейса \(<xref:System.Windows.LocalizationCategory>\), которые можно использовать для предоставления локализаторам дополнительного контекста.  Категории [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию для элементов управления платформы также могут переопределяться в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Атрибуты локализации по умолчанию, предоставляемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], также могут быть переопределены в коде, так что можно корректно установить правильные значения по умолчанию для пользовательских элементов управления.  Примеры.  
  
 `[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]`  
  
 `public class CorporateLogo: TextBlock`  
  
 `{`  
  
 `…`  
  
 `..`  
  
 `.`  
  
 `}`  
  
 Каждый набор атрибутов экземпляра, установленный в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], будет иметь приоритет над значениями, заданными в коде в пользовательских элементах управления.  Дополнительные сведения об атрибутах и комментариях см. в разделе [Атрибуты и комментарии локализации](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
 **Подмена шрифтов и составные шрифты**  
  
 Если задан шрифт, который не поддерживает данный диапазон кодовых точек, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будет автоматически подменять его шрифтом, который реализуется с помощью шрифта Global User Interface.compositefont, расположенного в папке Windows\\Fonts.  Составные шрифты работают так же, как и любой другой шрифт, и могут использоваться явно путем установки параметра FontFamily элемента \(например,  FontFamily\= "Global User Interface"\).  Можно задавать собственные предпочтения для подмены шрифта путем создания собственного составного шрифта и указания его использования для конкретных языков и диапазонов кода UNICODE.  
  
 Дополнительные сведения о составных шрифтах см. в разделе <xref:System.Windows.Media.FontFamily>.  
  
 **Локализация домашней страницы Microsoft**  
  
 Для локализации домашней страницы Microsoft можно выполнить те же действия, что и в примере локализации приложения диалогового окна "Выполнить".  Локализованный CSV\-файл для арабского языка доступен в разделе [Пример Globalization Homepage](http://go.microsoft.com/fwlink/?LinkID=159990).