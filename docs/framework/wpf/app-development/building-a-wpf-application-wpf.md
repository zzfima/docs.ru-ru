---
title: "Построение приложения WPF | Microsoft Docs"
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
  - "приложение WPF, построение"
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
caps.latest.revision: 45
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 42
---
# Построение приложения WPF
Приложения [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] могут быть построены как исполняемые файлы \(.exe\), библиотеки \(.dll\) или как комбинация обоих типов сборки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  В этом разделе приведены основные сведения о построении приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и описаны основные шаги процесса построения.  
  
   
  
<a name="Building_a_WPF_Application_using_Command_Line"></a>   
## Построение приложения WPF  
 Компиляцию приложения WPF можно выполнять следующими способами.  
  
-   Командная строка.  Приложение должно содержать только код \(без разметки XAML\) и файл определения приложения.  Дополнительные сведения см. в разделе [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Построение из командной строки \(Visual Basic\)](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md).  
  
-   Microsoft Build Engine \(MSBuild\).  Помимо кода и файлов XAML, приложение должно содержать файл проекта MSBuild.  Дополнительные сведения см. в разделе [MSBuild](../Topic/MSBuild1.md).  
  
-   Visual Studio.  Visual Studio — это интегрированная среда разработки, которая компилирует приложения WPF с помощью программы MSBuild. Она также включает визуальный конструктор для создания пользовательского интерфейса.  Дополнительные сведения см. в разделах [Разработка приложений в Visual Studio](http://msdn.microsoft.com/ru-ru/97490c1b-a247-41fb-8f2c-bc4c201eff68) и [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26).  
  
<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>   
## Конвейер построения WPF  
 Когда проект [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] собран, вызывается комбинация файлов целей, зависимых от конкретного языка и от [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Процесс выполнения этих файлов целей называется конвейер построения, его ключевые шаги показаны в следующей схеме.  
  
 ![Процесс построения WPF](../../../../docs/framework/wpf/app-development/media/wpfbuildsystem-figure1.png "WPFBuildSystem\_Figure1")  
  
<a name="Pre_Build_Initializations"></a>   
### Инициализации перед построением  
 Перед построением [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] определяет расположение важных средств и библиотек, в том числе следующих:  
  
-   [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  
  
-   Каталоги [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)].  
  
-   Расположение сборок ссылок [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   Свойство для путей поиска сборки.  
  
 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] в первую очередь выполняет поиск сборок в каталоге базовых сборок \(%ProgramFiles%\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\\).  На этом шаге процесс построения также инициализирует различные свойства и группы элементов, а также выполняет все необходимые работы по очистке.  
  
<a name="Resolving_references"></a>   
### Разрешение ссылок  
 Процесс построения находит и привязывает сборки, которые требуются для построения проекта приложения.  Логика процесса содержится в задаче `ResolveAssemblyReference`.  Все сборки, объявленные в файле проекта как `Reference`, предоставляются задаче вместе с информацией о путях поиска и метаданными о сборках, уже установленных в системе.  Задача ищет сборки и использует метаданные установленной сборки для фильтрации этих основных сборок [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], которые не должны отображаться в манифесте выходных данных.  Это делается, чтобы избежать избыточных данных в манифесте ClickOnce.  Например, так как PresentationFramework.dll может считаться представителем приложения, построенного на и для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и, кроме того, поскольку все сборки [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расположены в одном и том же месте на каждом компьютере, на котором установлен [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], нет необходимости включать в манифесты все сведения о всех сборках ссылок [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  
  
<a name="Markup_Compilation___Pass_1"></a>   
### Компиляция разметки — этап 1  
 На этом шаге файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксически разбираются и компилируются, чтобы среда выполнения далее не тратила время на разбор [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] и проверку значений свойств.  Скомпилированный файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] заранее размечен, так что во время выполнения его загрузка занимает намного меньше времени, чем загрузка файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 На этом шаге для каждого файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], являющегося элементом, построенным `Page`, выполняются следующие действия:  
  
1.  Файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разбирается компилятором разметки.  
  
2.  Для этого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] создается скомпилированное представление, затем оно копируется в папку obj\\Release.  
  
3.  Создается представление CodeDOM нового частичного класса, затем оно копируется в папку obj\\Release.  
  
 Кроме того, для каждого файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] создается зависящий от языка файл кода. Например, для страницы Page1.xaml в проекте [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)] создается файл Page1.g.vb, а для той же страницы в проекте [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] создается файл Page1.g.cs.  ".g" в имени файла показывает, что файл является созданным кодом с объявлением частичного класса для верхнеуровневого элемента файла разметки \(например, `Page` или `Window`\).  Класс объявлен в [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] с модификатором `partial` \(в [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)] с модификатором `Extends`\), означающим, что где\-то в другом месте есть другое объявление класса, обычно в файле кода программной части Page1.xaml.cs.  
  
 Частичный класс расширяется от соответствующего базового класса \(например, <xref:System.Windows.Controls.Page> для страницы\) и реализует интерфейс <xref:System.Windows.Markup.IComponentConnector?displayProperty=fullName>.  В интерфейсе <xref:System.Windows.Markup.IComponentConnector> есть методы инициализации компонента и связывания имен и событий элемента в его содержимом.  Следовательно, в созданном файле кода есть реализация метода, как, например, показано далее:  
  
```csharp  
public void InitializeComponent() {  
    if (_contentLoaded) {  
        return;  
    }  
    _contentLoaded = true;  
    System.Uri resourceLocater =   
        new System.Uri(  
            "window1.xaml",   
            System.UriKind.RelativeOrAbsolute);  
    System.Windows.Application.LoadComponent(this, resourceLocater);  
}  
```  
  
```vb  
Public Sub InitializeComponent() _  
  
    If _contentLoaded Then  
        Return  
    End If  
  
    _contentLoaded = True  
    Dim resourceLocater As System.Uri = _  
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)  
  
    System.Windows.Application.LoadComponent(Me, resourceLocater)  
  
End Sub  
```  
  
 По умолчанию компиляция разметки выполняется в том же <xref:System.AppDomain>, что и ядро [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].  Это обеспечивает значительное преимущество в производительности.  Такое поведение может быть переключено с помощью свойства `AlwaysCompileMarkupFilesInSeparateDomain`.  Так можно получить преимущество при выгрузке все сборок ссылок при выгрузке отдельного <xref:System.AppDomain>.  
  
<a name="Pass_2_of_Markup_Compilation"></a>   
### Компиляция разметки — этап 2  
 Не все страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] компилируются на этапе 1 компиляции разметки.  Файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], для которых локально определены ссылки на типы \(ссылки на типы, определенные в коде в другом месте того же проекта\), исключаются из компиляции на этом этапе.  Это происходит потому, что эти локально определенные типы существуют только в исходном коде и еще не скомпилированы.  Чтобы определить это, синтаксический анализатор использует эвристику, вызывающую поиск элементов, таких как `x:Name`, в файле разметки.  Если такой экземпляр обнаруживается, компиляция этого файла разметки откладывается до тех пор, пока файлы кода не будут скомпилированы, после чего второй этап компиляции разметки будет обрабатывать эти файлы.  
  
<a name="File_Classification"></a>   
### Классификация файлов  
 Процесс построения распределяет выходные файлы в различные группы ресурсов, основанные на том, в какой сборке приложения они будут расположены.  В обыкновенном нелокализованном приложении все файлы данных, отмеченные как `Resource`, располагаются в главной сборке \(исполняемом файле или библиотеке\).  Когда в проекте задан `UICulture`, все скомпилированные файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и ресурсы, специально отмеченные как специфичные для конкретного языка, помещаются в сопутствующую сборку ресурсов.  Кроме того, все нейтральные для языка ресурсы помещаются в основную сборку.  На этом шаге процесса построения производится определение.  
  
 Действия построения `ApplicationDefinition`, `Page` и `Resource` в файле проекта могут быть дополнены метаданными `Localizable` \(допустимые значения — `true` и `false`\), которые указывают, является ли файл зависящим или не зависящим от языка.  
  
<a name="Core_Compilation"></a>   
### Основная компиляция  
 На этапе основной компиляции осуществляется компиляция файлов кода.  Это происходит по логике, содержащейся в специфичных для языка файлах целей Microsoft.CSharp.targets и Microsoft.VisualBasic.targets..  Если эвристика определила, что первого этапа компилятора разметки достаточно, то создается основная сборка.  Тем не менее, если один или несколько файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в проекте имеют ссылки на локально определенные типы, то затем создается временный DLL\-файл, чтобы по завершении второго этапа компиляции разметки могли быть созданы окончательные сборки приложения.  
  
<a name="Manifest_generation"></a>   
### Создание манифеста  
 В конце процесса построения, при готовности всех сборок приложения и файлов содержимого, для приложения создаются манифесты [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)].  
  
 Файл манифеста развертывания описывает модель развертывания: текущую версию, поведение обновления и идентификатор издателя вместе с цифровой подписью.  Этот манифест должен быть написан администраторами, управляющими развертыванием.  Расширение файла: XBAP \(для [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]\) и APPLICATION для установленных приложений.  Первое расширение определяется свойством `HostInBrowser` проекта, и в результате манифест идентифицирует приложение как приложение, размещенное в браузере.  
  
 Манифест приложения \(файл .exe.manifest\) описывает сборки приложения и зависимые библиотеки и перечисляет разрешения, необходимые для приложения.  Этот файл должен быть написан разработчиком приложения.  Чтобы запустить приложение [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], пользователь открывает файл манифеста развертывания приложения.  
  
 Эти файлы манифеста всегда создаются для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Для установленных приложений они не создаются, если в файле проекта свойство `GenerateManifests` не имеет значение `true`.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] получают два дополнительных и более высокоприоритетных разрешения, чем присвоенные обычным приложениям зоны "Интернет": <xref:System.Security.Permissions.WebBrowserPermission> и <xref:System.Security.Permissions.MediaPermission>.  Система построения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] объявляет эти разрешения в манифесте приложения.  
  
<a name="Incremental_Build_Support"></a>   
## Поддержка инкрементного построения  
 Система построения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] обеспечивает поддержку инкрементного построения.  Она довольно умело обнаруживает изменения в разметке и коде, и она компилирует только те фрагменты, на которые влияют изменения.  Механизм инкрементного построения использует следующие файлы:  
  
-   Файл $\(*AssemblyName*\)\_MarkupCompiler.Cache для поддержания текущего состояния компилятора.  
  
-   Файл $\(*AssemblyName*\)\_MarkupCompiler.lref для кэширования файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] со ссылками на локально определенные типы.  
  
 Ниже приведен набор правил, управляющих инкрементным построением:  
  
-   Файл является наименьшей единицей, в которой система построения обнаруживает изменения.  Таким образом, для файла кода система построения не может определить, был ли изменен тип или добавлен код.  То же самое касается и файлов проекта.  
  
-   Механизм инкрементного построения должен знать, определяет ли страница [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] класс или использует другие классы.  
  
-   При изменении `Reference` перекомпилируются все страницы.  
  
-   При изменении файла кода перекомпилируются все страницы с локально определенными ссылками типа.  
  
-   При изменении файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
    -   Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] объявлен в проекте как `Page`: если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не имеет локально определенных ссылок типа, перекомпилируется этот [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] плюс все страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с локальными ссылками; если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имеет локальные ссылки, перекомпилируются все страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с локальными ссылками.  
  
    -   Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] объявлен в проекте как `ApplicationDefinition`: перекомпилируются все страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(поскольку во всех [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] есть ссылка на тип <xref:System.Windows.Application>, который возможно был изменен\).  
  
-   Если файл проекта объявляет файл кода как определение приложения вместо файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
    -   Проверяется, изменилось ли значение `ApplicationClassName` в файле проекта \(есть ли новый тип приложения?\).  Если это так, перекомпилируется все приложение.  
  
    -   В противном случае перекомпилируются все страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с локальными ссылками.  
  
-   При изменении файла проекта применяются все вышеперечисленные правила и проверяется, что должно быть перекомпилировано.  Изменения следующих свойств приводят к полной перекомпиляции: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace` и `HostInBrowser`.  
  
 Возможны следующие сценарии перекомпиляции:  
  
-   Перекомпилируется все приложение.  
  
-   Перекомпилируются только те файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], в которых есть локально определенные ссылки типа.  
  
-   Ничего не перекомпилируется \(если в проекте ничего не было изменено\).  
  
## См. также  
 [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [Справочные сведения о WPF для MSBuild](../Topic/WPF%20MSBuild%20Reference.md)   
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)