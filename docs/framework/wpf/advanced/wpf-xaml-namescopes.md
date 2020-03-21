---
title: Пространства имен XAML
ms.date: 03/30/2017
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
ms.openlocfilehash: f9d4439c6b102d0d430b5201e3649985daee0b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186272"
---
# <a name="wpf-xaml-namescopes"></a>Области видимости имен XAML в WPF
Области имен XAML — это понятие, которое идентифицирует объекты, определенные в XAML. Имена из области имен XAML можно использовать для установления связей между именами объектов, определенными в XAML, и эквивалентными им экземплярами из дерева объектов. Области имен XAML в управляемом коде [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], как правило, создаются при загрузке отдельных корневых страниц XAML для приложения XAML. XAML namescopes как объект программирования <xref:System.Windows.Markup.INameScope> определяются интерфейсом и <xref:System.Windows.NameScope>также реализуются практическим классом.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>
## <a name="namescopes-in-loaded-xaml-applications"></a>Области имен в загруженных приложениях XAML  
 В более широком контексте программирования или информатики в концепции программирования включается принцип уникального идентификатора или имени, которое можно использовать для доступа к объекту. В системах, где используются идентификаторы или имена, область имен определяет границы, в пределах которых процесс или технология ищет объект с запрошенным именем, или границы, в пределах которых применяются уникальные имена. Эти общие принципы действительны и для областей имен XAML. В WPF области имен XAML создаются в корневом элементе страницы XAML при загрузке страницы. Каждое имя, указанное внутри страницы XAML, начиная с корневой страницы, добавляется в соответствующую область имен XAML.  
  
 В WPF XAML элементы, которые являются <xref:System.Windows.Controls.Page>общими корневыми элементами (например, и <xref:System.Windows.Window>) всегда управляют именем XAML. Если элемент, <xref:System.Windows.FrameworkElement> такой <xref:System.Windows.FrameworkContentElement> как или является корневым элементом страницы в разметке, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор добавляет <xref:System.Windows.Controls.Page> корень неявно, так что <xref:System.Windows.Controls.Page> может обеспечить рабочий XAML namescope.  
  
> [!NOTE]
> Область имен XAML создается для рабочего приложения XAML при выполнении действий сборки WPF, даже если атрибуты `Name` и `x:Name` не определены в элементах разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 При попытке использования одного и того же имени дважды в любой области имен XAML будет вызвано исключение. Для кода XAML системы WPF, который содержит код программной части и является компонентом скомпилированного приложения, во время первоначальной компиляции разметки при создании сформированного класса для страницы вызывается исключение при выполнении действий сборки WPF. Для кода XAML, разметка которого не скомпилирована действием сборки, исключения, связанные с проблемами области имен XAML, могут вызываться при загрузке кода XAML. Разработчики XAML должны также учитывать возможность возникновения проблем с областью имен XAML во время разработки.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Добавление объектов в деревья объектов среды выполнения  
 Область имен XAML системы WPF создается и определяется в момент синтаксического анализа кода XAML. Если объект добавляется в дерево объектов уже после того, как выполнен синтаксический анализ кода XAML, сформировавшего это дерево, значение `Name` или `x:Name` нового объекта не приводит к автоматическому обновлению сведений из области имен XAML. Чтобы добавить имя объекта в namescope WPF XAML после загрузки XAML, <xref:System.Windows.Markup.INameScope.RegisterName%2A> необходимо вызвать соответствующую реализацию на объекте, который определяет xAML namescope, который обычно является корнем страницы XAML. Если имя не зарегистрировано, добавленный объект не может быть <xref:System.Windows.FrameworkElement.FindName%2A>отсылкой по имени с помощью таких методов, как, и вы не можете использовать это имя для таргетинга анимации.  
  
 Наиболее распространенным сценарием для разработчиков приложений является то, что вы будете использовать <xref:System.Windows.FrameworkElement.RegisterName%2A> для регистрации имен в namescope XAML на текущем корне страницы. <xref:System.Windows.FrameworkElement.RegisterName%2A>является частью важного сценария для раскадровок, которые нацелены на объекты для анимации. Дополнительные сведения см. в разделе [Общие сведения о Storyboard](../graphics-multimedia/storyboards-overview.md).  
  
 Если вы <xref:System.Windows.FrameworkElement.RegisterName%2A> вызываете объект, отличный от объекта, определяющего имя XAML, имя по-прежнему зарегистрировано в namescope XAML, в котором находится объект вызова, как если бы вы призвали <xref:System.Windows.FrameworkElement.RegisterName%2A> к определению объекта XAML namescope.  
  
### <a name="xaml-namescopes-in-code"></a>Области имен XAML в коде  
 Вы можете создавать и использовать области имен XAML в коде. Интерфейсы API и понятия, которые применяются при создании областей имен XAML, совпадают с применяемыми в чистом коде, так как обработчик XAML для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует эти API и понятия при обработке самого кода XAML. Они существуют в основном для поиска объектов по имени в дереве объектов, которое, как правило, частично или полностью задано в XAML.  
  
 Для приложений, которые создаются программно, а не из загруженного XAML, объект, <xref:System.Windows.Markup.INameScope>определяющий <xref:System.Windows.FrameworkElement> XAML namescope, должен реализовать, или быть классом или <xref:System.Windows.FrameworkContentElement> производным, чтобы поддержать создание XAML namescope на своих экземплярах.  
  
 Также для любого элемента, не загруженного и не обработанного обработчиком XAML, область имен XAML для объекта не создается и не инициализируется по умолчанию. Необходимо явным образом создать область имен XAML для любого объекта, в котором впоследствии требуется регистрировать имена. Чтобы создать XAML namescope, вы <xref:System.Windows.NameScope.SetNameScope%2A> называете статический метод. Укажите объект, который будет `dependencyObject` владеть им <xref:System.Windows.NameScope.%23ctor%2A> в качестве `value` параметра, и вызов нового конструктора в качестве параметра.  
  
 Если объект, `dependencyObject` <xref:System.Windows.NameScope.SetNameScope%2A> предусмотренный <xref:System.Windows.Markup.INameScope> как для <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>не <xref:System.Windows.FrameworkElement.RegisterName%2A> является реализацией, или , призыв к любым элементам ребенка не будет иметь никакого эффекта. Если вы не сможете создать новый XAML <xref:System.Windows.FrameworkElement.RegisterName%2A> namescope явно, то вызовы поднимут исключение.  
  
 Пример использования интерфейсов API для области имен XAML в коде см. в разделе [Определение пространства имен](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>
## <a name="xaml-namescopes-in-styles-and-templates"></a>Области имен XAML в стилях и шаблонах  
 Стили и шаблоны [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяют повторно использовать и применять содержимое простым и понятным способом. Однако стили и шаблоны могут также включать элементы с именами XAML, определенными на уровне шаблона. Затем один и тот же шаблон может использоваться несколько раз на странице. По этой причине стили и шаблоны определяют свои собственные области имен XAML независимо от расположения в дереве объектов, где применяется стиль или шаблон.  
  
 Рассмотрим следующий пример:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Здесь один тот же шаблон применяется к двум разным кнопкам. Если у шаблонов не было дискретных областей имен XAML, имя `TheBorder`, используемое в шаблоне, вызовет конфликт имен в области имен XAML. Каждый экземпляр шаблона имеет свою собственную область имен XAML, поэтому в данном примере каждая область имен XAML экземпляра шаблона будет содержать ровно одно имя.  
  
 Стили также определяют собственные области имен XAML, в основном поэтому части раскадровок могут иметь присвоенные индивидуальные имена. Эти имена включают конкретные расширения функциональности элемента управления, которые предназначены для элементов с таким именем, даже если шаблон был переопределен при настройке элемента управления.  
  
 Из-за независимых областей имен XAML поиск именованных элементов в шаблоне является более затратной задачей, чем поиск нешаблонного именованного элемента на странице. Сначала необходимо определить прикладной шаблон, <xref:System.Windows.Controls.Control.Template%2A> получив значение свойства элемента управления, в котором применяется шаблон. Затем вы называете шаблон <xref:System.Windows.FrameworkTemplate.FindName%2A>версии, проходя элемент управления, где шаблон был применен в качестве второго параметра.  
  
 Если вы являетесь автором элемента управления и создаете конвенцию, в которой конкретный названный элемент в прикладном шаблоне является мишенью для поведения, определяемого самим элементом управления, можно использовать <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> метод из кода реализации элемента управления. Метод <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> защищен, поэтому доступ к нему имеет только автор элемента управления.  
  
 Если вы работаете из шаблона, и нужно добраться до XAML namescope, <xref:System.Windows.FrameworkElement.TemplatedParent%2A>где применяется <xref:System.Windows.FrameworkElement.FindName%2A> шаблон, получить значение , а затем позвонить туда. В качестве примера работы в шаблоне можно привести ситуацию, когда пишется реализация обработчика событий, в котором событие будет вызвано из элемента в примененном шаблоне.  
  
<a name="Namescopes_and_Name_related_APIs"></a>
## <a name="xaml-namescopes-and-name-related-apis"></a>Области имен XAML и интерфейсы API, связанные с именами  
 <xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkElement.FindName%2A>имеет, <xref:System.Windows.FrameworkElement.RegisterName%2A> <xref:System.Windows.FrameworkElement.UnregisterName%2A> и методы. Если объект, для которого вызываются эти методы, имеет собственную область имен XAML, то методы вызывают методы соответствующей области имен XAML. В противном случае выполняется проверка того, владеет ли родительский элемент областью имен XAML и этот процесс продолжается рекурсивно до тех пор, пока область имен XAML не будет найдена (из-за того что поведение обработчика XAML гарантирует наличие области имен XAML в корне). <xref:System.Windows.FrameworkContentElement>имеет аналогичное поведение, за исключением того, что никогда не <xref:System.Windows.FrameworkContentElement> будет владеть XAML namescope. Методы существуют <xref:System.Windows.FrameworkContentElement> на так, что вызовы <xref:System.Windows.FrameworkElement> могут быть направлены в конечном итоге в родительский элемент.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>используется для отображения нового xAML namescope к существующему объекту. Вы можете <xref:System.Windows.NameScope.SetNameScope%2A> вызвать несколько раз, чтобы сбросить или очистить XAML namescope, но это не является распространенным использованием. Кроме <xref:System.Windows.NameScope.GetNameScope%2A> того, обычно не используется из кода.  
  
### <a name="xaml-namescope-implementations"></a>Реализации области имен XAML  
 Следующие классы реализуются <xref:System.Windows.Markup.INameScope> непосредственно:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>не использует имена XAML или namescopes; вместо этого он использует ключи, потому что это реализация словаря. Единственная <xref:System.Windows.ResourceDictionary> причина, <xref:System.Windows.Markup.INameScope> по которой реализуется, заключается в том, что они могут вызывать исключения <xref:System.Windows.ResourceDictionary> для пользовательского кода, которые помогают прояснить различие между <xref:System.Windows.ResourceDictionary> истинным именем XAML и тем, как обрабатывает клавиши, а также гарантировать, что имена XAML не применяются к родительским элементам.  
  
 <xref:System.Windows.FrameworkTemplate>и <xref:System.Windows.Style> <xref:System.Windows.Markup.INameScope> осуществлять через четкие определения интерфейса. Явные реализации позволяют этим xAML namescopes вести себя <xref:System.Windows.Markup.INameScope> условно, когда они доступны через интерфейс, который [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является, как XAML namescopes передаются внутренние процессы. Но явные определения интерфейса не являются частью <xref:System.Windows.Style>обычной поверхности API <xref:System.Windows.Markup.INameScope> <xref:System.Windows.FrameworkTemplate> и, <xref:System.Windows.Style> потому что вам редко нужно <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>вызывать методы на <xref:System.Windows.FrameworkTemplate> и непосредственно, и вместо этого будет использовать другие API, такие как .  
  
 Следующие классы определяют свой собственный XAML namescope, используя класс <xref:System.Windows.NameScope?displayProperty=nameWithType> помощника и подключившись к реализации XAML namescope через <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> прилагаемое свойство:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>См. также раздел

- [Пространства имен XAML и сопоставление пространств имен для WPF XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [Директива x:Name](../../../desktop-wpf/xaml-services/xname-directive.md)
