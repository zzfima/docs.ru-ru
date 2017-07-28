---
title: "Объединенные словари ресурсов | Microsoft Docs"
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
  - "объединенные словари ресурсов"
  - "словари, объединенные ресурсы"
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Объединенные словари ресурсов
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ресурсы поддерживают функцию объединенного словаря ресурсов. Эта функция обеспечивает возможность определения части ресурсов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] за пределами скомпилированного приложения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] приложения. Ресурсы можно использовать совместно в приложениях и также более удобного изолируются для локализации.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Представляем объединенного словаря ресурсов  
 В разметке используйте следующий синтаксис для представления объединенного словаря ресурсов на странице:  
  
 [!code-xml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Обратите внимание, что <xref:System.Windows.ResourceDictionary> элемент не имеет [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md), которая обычно используется для всех элементов в коллекции ресурсов. Но другой <xref:System.Windows.ResourceDictionary> ссылки <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекция является особым случаем, зарезервированным для этого скрипта объединенного словаря ресурсов. <xref:System.Windows.ResourceDictionary> представляющий объединенный словарь ресурсов не может быть [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md). Как правило, каждый <xref:System.Windows.ResourceDictionary> в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> указывает коллекцию <xref:System.Windows.ResourceDictionary.Source%2A> атрибута. Значение <xref:System.Windows.ResourceDictionary.Source%2A> должно быть [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] , разрешает путь к файлу ресурсов для слияния. Место назначения, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] должен быть другой [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла, с <xref:System.Windows.ResourceDictionary> в качестве корневого элемента.  
  
> [!NOTE]
>  Можно определять ресурсы в <xref:System.Windows.ResourceDictionary> , который указан как объединенный словарь, либо в качестве альтернативы заданию <xref:System.Windows.ResourceDictionary.Source%2A>, или в дополнение к включаются любые ресурсы из указанного источника. Однако это не очень часто; основным сценарием для объединенных словарей является объединение ресурсов из внешних файлов. Если требуется указать ресурсы внутри разметки страницы, обычно следует определить их в главном <xref:System.Windows.ResourceDictionary> , а не в объединенных словарях.  
  
## <a name="merged-dictionary-behavior"></a>Режим объединенного словаря  
 Ресурсы в объединенном словаре занимают место в области поиска ресурсов, располагающейся сразу после области основного словаря ресурсов, они будут объединены. Хотя ключ ресурса должен быть уникальным в пределах одного словаря, ключ может существовать несколько раз в наборе объединенных словарей. В этом случае возвращаемый ресурс поступит из последнего словаря, последовательно найденного в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекции. Если <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекции был определен в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], то порядок объединенных словарей в коллекции является порядок элементов в разметке. Если ключ определен в основном словаре, а также в объединенном словаре, возвращаемый ресурс поступит из основного словаря. Эти правила поиска применяются одинаково для ссылки на ресурсы для статических и динамических ресурсов ссылки.  
  
### <a name="merged-dictionaries-and-code"></a>Объединенные словари и программный код  
 Объединенные словари могут быть добавлены к `Resources` словарь с помощью кода. По умолчанию, первоначально пустого <xref:System.Windows.ResourceDictionary> , существует для `Resources` свойство также имеет значение по умолчанию, первоначально пустого <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> свойства коллекции. Добавление объединенного словаря посредством кода, можно получить ссылку на нужный источник <xref:System.Windows.ResourceDictionary>, получить его <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> значение свойства и вызвать `Add` универсального `Collection` , содержащимся в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Добавляемый объект должен быть новый <xref:System.Windows.ResourceDictionary>. В коде не задано <xref:System.Windows.ResourceDictionary.Source%2A> свойство. Вместо этого необходимо получить <xref:System.Windows.ResourceDictionary> объекта путем создания одного или загрузку. Один из способов загрузки существующего <xref:System.Windows.ResourceDictionary> для вызова <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> на существующем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлового потока с <xref:System.Windows.ResourceDictionary> корень, затем приведение <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> возвращаемое значение для <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>Идентификаторы URI словарь объединенных ресурсов  
 Существует несколько методов включения объединенного словаря ресурсов, который указан в [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] формате, который будет использоваться. Вообще говоря, эти методы можно разделить на две категории: ресурсы, которые компилируются как часть проекта и ресурсы, которые не компилируются как часть проекта.  
  
 Для ресурсов, которые компилируются как часть проекта можно использовать относительный путь, который ссылается на расположение ресурса. Относительный путь вычисляется во время компиляции. Ресурс должен быть определен как часть проекта в качестве действия построения ресурса. Если включить XAML-файл ресурсов в проект в качестве ресурса, необходимо скопировать файл ресурсов в выходной каталог, ресурс уже включен в скомпилированном приложении. Можно также использовать действие построения содержимого, но необходимо также развернуть файлы ресурсов в одной и той же связи путь к исполняемому файлу и скопируйте файлы в выходной каталог.  
  
> [!NOTE]
>  Не используйте действие построения внедренного ресурса. Само действие построения поддерживается для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения, но разрешение <xref:System.Windows.ResourceDictionary.Source%2A> не могут содержать <xref:System.Resources.ResourceManager>и поэтому невозможно выделение отдельного ресурса из потока. Внедренный ресурс по-прежнему можно использовать для других целей до тех пор, пока используется <xref:System.Resources.ResourceManager> доступ к ресурсам.  
  
 Близкой методикой является использование пакета URI для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл и ссылка на него в качестве источника. Пакет URI позволяет ссылки на компоненты сборок и другие методы. Дополнительные сведения о пакетах Pack URI см. в разделе [ресурса приложения WPF, содержимое и файлы данных](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Для ресурсов, которые не компилируются как часть проекта URI обрабатывается во время выполнения. Например, файл можно использовать общий транспорт URI: или http: для ссылки на файл ресурсов. Этот файл является недостатком подхода некомпилированный ресурс: доступа требует дополнительных действий по развертыванию и http: доступ подразумевает безопасности зоны Интернета.  
  
### <a name="reusing-merged-dictionaries"></a>Повторное использование объединенных словарей  
 Можно использовать повторно или совместно использовать объединенные словари ресурсов между приложениями, поскольку словарь ресурсов, предназначенный для слияния, можно ссылаться через любые допустимые [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Точно, как сделать это будет зависеть от стратегии развертывания приложения и какая модель приложение выполняется выполните. Вышеупомянутая стратегия Pack URI обеспечивает способ обращения к объединенному ресурсу в нескольких проектах во время разработки, совместное использование ссылки на сборку. В этом случае ресурсы по-прежнему распространяются клиентом, и по крайней мере одно из приложений необходимо развернуть ссылочной сборки. Можно также ссылаться на объединенные ресурсы через распределенный URI, который использует протокол http.  
  
 Запись объединенных словарей как локальных файлов приложения или в локальное общее хранилище является другим возможные объединенного словаря или сценария развертывания приложения.  
  
### <a name="localization"></a>Локализация  
 Если ресурсы, которые необходимо локализовать, изолированы от словарей, объединенных в основные словари и хранятся как свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], эти файлы могут быть локализованы отдельно. Этот способ является упрощенной альтернативой для локализации сопутствующих сборок ресурсов. Дополнительные сведения см. в разделе [Обзор локализации и глобализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.ResourceDictionary>   
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [Ресурс приложения WPF, содержимое и файлы данных](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)