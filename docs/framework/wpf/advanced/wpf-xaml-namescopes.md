---
title: Области видимости имен XAML в WPF
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
ms.openlocfilehash: edf5c8a828bea182cd87542276fb7eb2df1908be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917328"
---
# <a name="wpf-xaml-namescopes"></a>Области видимости имен XAML в WPF
Области имен XAML — это понятие, которое идентифицирует объекты, определенные в XAML. Имена из области имен XAML можно использовать для установления связей между именами объектов, определенными в XAML, и эквивалентными им экземплярами из дерева объектов. Области имен XAML в управляемом коде [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], как правило, создаются при загрузке отдельных корневых страниц XAML для приложения XAML. Области имен XAML, так как программный объект определяются <xref:System.Windows.Markup.INameScope> интерфейсом и также реализуются практическим классом <xref:System.Windows.NameScope>.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Области имен в загруженных приложениях XAML  
 В более широком контексте программирования или информатики в концепции программирования включается принцип уникального идентификатора или имени, которое можно использовать для доступа к объекту. В системах, где используются идентификаторы или имена, область имен определяет границы, в пределах которых процесс или технология ищет объект с запрошенным именем, или границы, в пределах которых применяются уникальные имена. Эти общие принципы действительны и для областей имен XAML. В WPF области имен XAML создаются в корневом элементе страницы XAML при загрузке страницы. Каждое имя, указанное внутри страницы XAML, начиная с корневой страницы, добавляется в соответствующую область имен XAML.  
  
 В WPF XAML элементы, являющиеся общими корневыми элементами (например <xref:System.Windows.Controls.Page>, и <xref:System.Windows.Window>), всегда управляют областью имен XAML. <xref:System.Windows.FrameworkElement> Если элемент [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.FrameworkContentElement> ,например<xref:System.Windows.Controls.Page> или, является корневым элементом страницы в разметке, обработчик неявно добавляет корень,чтобыможнобылопредоставитьрабочуюобластьвидимостиXAML.<xref:System.Windows.Controls.Page>  
  
> [!NOTE]
> Область имен XAML создается для рабочего приложения XAML при выполнении действий сборки WPF, даже если атрибуты `Name` и `x:Name` не определены в элементах разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 При попытке использования одного и того же имени дважды в любой области имен XAML будет вызвано исключение. Для кода XAML системы WPF, который содержит код программной части и является компонентом скомпилированного приложения, во время первоначальной компиляции разметки при создании сформированного класса для страницы вызывается исключение при выполнении действий сборки WPF. Для кода XAML, разметка которого не скомпилирована действием сборки, исключения, связанные с проблемами области имен XAML, могут вызываться при загрузке кода XAML. Разработчики XAML должны также учитывать возможность возникновения проблем с областью имен XAML во время разработки.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Добавление объектов в деревья объектов среды выполнения  
 Область имен XAML системы WPF создается и определяется в момент синтаксического анализа кода XAML. Если объект добавляется в дерево объектов уже после того, как выполнен синтаксический анализ кода XAML, сформировавшего это дерево, значение `Name` или `x:Name` нового объекта не приводит к автоматическому обновлению сведений из области имен XAML. Чтобы добавить имя объекта в область имен XAML WPF после загрузки XAML, необходимо вызвать соответствующую реализацию <xref:System.Windows.Markup.INameScope.RegisterName%2A> для объекта, определяющего область имен XAML, которая обычно является корнем страницы XAML. Если имя не зарегистрировано, на добавленный объект нельзя ссылаться по имени с помощью методов, таких <xref:System.Windows.FrameworkElement.FindName%2A>как, и его нельзя использовать для нацеленности на анимацию.  
  
 Наиболее распространенным сценарием для разработчиков приложений является то, что <xref:System.Windows.FrameworkElement.RegisterName%2A> вы будете использовать для регистрации имен в области имен XAML в текущем корне страницы. <xref:System.Windows.FrameworkElement.RegisterName%2A>является частью важного сценария для раскадровок, предназначенных для объектов анимации. Дополнительные сведения см. в разделе [Общие сведения о Storyboard](../graphics-multimedia/storyboards-overview.md).  
  
 При вызове <xref:System.Windows.FrameworkElement.RegisterName%2A> для объекта, отличного от объекта, определяющего область имен XAML, имя по-прежнему регистрируется в области имен XAML, в которой содержится вызывающий объект, как если бы <xref:System.Windows.FrameworkElement.RegisterName%2A> вызывался объект, определяющий область имен XAML.  
  
### <a name="xaml-namescopes-in-code"></a>Области имен XAML в коде  
 Вы можете создавать и использовать области имен XAML в коде. Интерфейсы API и понятия, которые применяются при создании областей имен XAML, совпадают с применяемыми в чистом коде, так как обработчик XAML для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует эти API и понятия при обработке самого кода XAML. Они существуют в основном для поиска объектов по имени в дереве объектов, которое, как правило, частично или полностью задано в XAML.  
  
 Для приложений, которые создаются программно, а не из загруженного XAML, объект, определяющий область имен XAML <xref:System.Windows.Markup.INameScope>, должен реализовывать или <xref:System.Windows.FrameworkElement> быть <xref:System.Windows.FrameworkContentElement> производным классом для поддержки создания области видимости имен XAML на его вхождений.  
  
 Также для любого элемента, не загруженного и не обработанного обработчиком XAML, область имен XAML для объекта не создается и не инициализируется по умолчанию. Необходимо явным образом создать область имен XAML для любого объекта, в котором впоследствии требуется регистрировать имена. Для создания области имен XAML вызывается статический <xref:System.Windows.NameScope.SetNameScope%2A> метод. Укажите объект, который будет владельцем его в качестве `dependencyObject` параметра, и новый <xref:System.Windows.NameScope.%23ctor%2A> вызов конструктора в качестве `value` параметра.  
  
 `dependencyObject` Если объект, <xref:System.Windows.NameScope.SetNameScope%2A> <xref:System.Windows.Markup.INameScope> <xref:System.Windows.FrameworkElement.RegisterName%2A> предоставленный как, не является реализацией или <xref:System.Windows.FrameworkContentElement>, вызов для всех дочерних элементов не будет действовать. <xref:System.Windows.FrameworkElement> Если не удается явно создать область видимости имен XAML, вызывает метод, чтобы <xref:System.Windows.FrameworkElement.RegisterName%2A> вызвать исключение.  
  
 Пример использования интерфейсов API для области имен XAML в коде см. в разделе [Определение пространства имен](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>Области имен XAML в стилях и шаблонах  
 Стили и шаблоны [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяют повторно использовать и применять содержимое простым и понятным способом. Однако стили и шаблоны могут также включать элементы с именами XAML, определенными на уровне шаблона. Затем один и тот же шаблон может использоваться несколько раз на странице. По этой причине стили и шаблоны определяют свои собственные области имен XAML независимо от расположения в дереве объектов, где применяется стиль или шаблон.  
  
 Рассмотрим следующий пример.  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Здесь один тот же шаблон применяется к двум разным кнопкам. Если у шаблонов не было дискретных областей имен XAML, имя `TheBorder`, используемое в шаблоне, вызовет конфликт имен в области имен XAML. Каждый экземпляр шаблона имеет свою собственную область имен XAML, поэтому в данном примере каждая область имен XAML экземпляра шаблона будет содержать ровно одно имя.  
  
 Стили также определяют собственные области имен XAML, в основном поэтому части раскадровок могут иметь присвоенные индивидуальные имена. Эти имена включают конкретные расширения функциональности элемента управления, которые предназначены для элементов с таким именем, даже если шаблон был переопределен при настройке элемента управления.  
  
 Из-за независимых областей имен XAML поиск именованных элементов в шаблоне является более затратной задачей, чем поиск нешаблонного именованного элемента на странице. Сначала необходимо определить примененный шаблон, получая <xref:System.Windows.Controls.Control.Template%2A> значение свойства элемента управления, в котором применяется шаблон. Затем вызывается версия <xref:System.Windows.FrameworkTemplate.FindName%2A>шаблона, передавая элемент управления, в котором шаблон был применен в качестве второго параметра.  
  
 Если вы являетесь автором элемента управления и создаете соглашение, в котором определенный именованный элемент в примененном шаблоне является целью для поведения, определяемого самим элементом управления, можно использовать <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> метод из кода реализации элемента управления. <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Метод защищен, поэтому доступ к нему имеют только автор элемента управления.  
  
 Если вы работаете в шаблоне и хотите перейти к области имен XAML, где применяется шаблон, получите значение <xref:System.Windows.FrameworkElement.TemplatedParent%2A>, а затем вызовите <xref:System.Windows.FrameworkElement.FindName%2A> его. В качестве примера работы в шаблоне можно привести ситуацию, когда пишется реализация обработчика событий, в котором событие будет вызвано из элемента в примененном шаблоне.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>Области имен XAML и интерфейсы API, связанные с именами  
 <xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkElement.FindName%2A>методы и.<xref:System.Windows.FrameworkElement.RegisterName%2A> <xref:System.Windows.FrameworkElement.UnregisterName%2A> Если объект, для которого вызываются эти методы, имеет собственную область имен XAML, то методы вызывают методы соответствующей области имен XAML. В противном случае выполняется проверка того, владеет ли родительский элемент областью имен XAML и этот процесс продолжается рекурсивно до тех пор, пока область имен XAML не будет найдена (из-за того что поведение обработчика XAML гарантирует наличие области имен XAML в корне). <xref:System.Windows.FrameworkContentElement>имеет аналогичные поведения, за исключением того, <xref:System.Windows.FrameworkContentElement> что ни один из них не владеет областью имен XAML. Методы существуют в <xref:System.Windows.FrameworkContentElement> , так что вызовы могут пересылаться в конечном итоге <xref:System.Windows.FrameworkElement> в родительский элемент.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>используется для соответствия новой области имен XAML существующему объекту. Можно вызвать <xref:System.Windows.NameScope.SetNameScope%2A> несколько раз, чтобы сбросить или очистить область имен XAML, но это не является распространенным использованием. Кроме того <xref:System.Windows.NameScope.GetNameScope%2A> , обычно не используется из кода.  
  
### <a name="xaml-namescope-implementations"></a>Реализации области имен XAML  
 Следующие классы реализуют <xref:System.Windows.Markup.INameScope> напрямую:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>не использует имена или области видимости имен XAML; Вместо этого используются ключи, так как это реализация словаря. Единственная причина, с <xref:System.Windows.ResourceDictionary> которой <xref:System.Windows.Markup.INameScope> реализуется, заключается в том, что она может вызывать исключения в пользовательском коде, которые помогают объяснить различие между истинной областью видимости имен <xref:System.Windows.ResourceDictionary> XAML и тем, как обработчики ключей, а также убедиться, что области имен XAML не применяются к элементу <xref:System.Windows.ResourceDictionary> по родительским элементам.  
  
 <xref:System.Windows.FrameworkTemplate>и <xref:System.Windows.Style> реализуйте <xref:System.Windows.Markup.INameScope> через явные определения интерфейса. Явные реализации позволяют этим областям видимости имен XAML вести себя по соглашению, когда доступ к ним осуществляется <xref:System.Windows.Markup.INameScope> через интерфейс, что заключается в том, как области имен XAML [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] взаимодействуют внутренними процессами. Но явные определения интерфейса не являются частью <xref:System.Windows.FrameworkTemplate> стандартной API-интерфейса и <xref:System.Windows.Style>, так как <xref:System.Windows.Markup.INameScope> редко приходится вызывать методы в <xref:System.Windows.FrameworkTemplate> и <xref:System.Windows.Style> напрямую, а вместо этого использовать другой API. <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>например.  
  
 Следующие классы определяют собственную область имен XAML с помощью <xref:System.Windows.NameScope?displayProperty=nameWithType> вспомогательного класса и подключаются к своей реализации области видимости имен XAML с <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> помощью присоединенного свойства:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>См. также

- [Пространства имен XAML и сопоставление пространств имен для WPF XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [Директива x:Name](../../xaml-services/x-name-directive.md)
