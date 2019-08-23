---
title: Объединенные словари ресурсов
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: 466a18a58acfebf6d779a1d0eba3d2637743806e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911725"
---
# <a name="merged-resource-dictionaries"></a>Объединенные словари ресурсов
Ресурсы [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поддерживают функцию объединенных словарей ресурсов. Эта функция обеспечивает способ определения части ресурсов приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] за пределами скомпилированного приложения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Затем ресурсы можно совместно использовать в приложениях; они также более удобно изолируются для локализации.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Общие сведения об объединенном словаре ресурсов  
 Для представления на странице объединенного словаря ресурсов используйте в разметке следующий синтаксис.  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Обратите внимание <xref:System.Windows.ResourceDictionary> , что элемент не имеет [директивы x:Key](../../xaml-services/x-key-directive.md), которая обычно требуется для всех элементов в коллекции ресурсов. Но еще <xref:System.Windows.ResourceDictionary> одна ссылка <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> в коллекции является особым случаем, зарезервированной для этого сценария объединенного словаря ресурсов. Объект <xref:System.Windows.ResourceDictionary> , который представляет объединенный словарь ресурсов, не может иметь [директиву x:Key](../../xaml-services/x-key-directive.md). Как правило, <xref:System.Windows.ResourceDictionary> каждый <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> в коллекции задает <xref:System.Windows.ResourceDictionary.Source%2A> атрибут. Значение <xref:System.Windows.ResourceDictionary.Source%2A> должно[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] быть значением, которое разрешается в расположение объединяемого файла ресурсов. Целевой объект [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] должен быть другим [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлом, в <xref:System.Windows.ResourceDictionary> качестве корневого элемента.  
  
> [!NOTE]
> Допускается определение ресурсов в <xref:System.Windows.ResourceDictionary> , которые указываются в виде объединенного словаря, либо в качестве альтернативы указанию <xref:System.Windows.ResourceDictionary.Source%2A>, либо в дополнение к любым ресурсам, включенным в указанный источник. Однако это не очень распространенный сценарий; основным сценарием для объединенных словарей является объединение ресурсов из внешних файлов. Если вы хотите указать ресурсы в разметке для страницы, обычно их следует определить в основном <xref:System.Windows.ResourceDictionary> , а не в Объединенных словарях.  
  
## <a name="merged-dictionary-behavior"></a>Поведение объединенного словаря  
 Ресурсы в объединенном словаре занимают место в области поиска ресурсов сразу после области главного словаря ресурсов, в который они будут включены. Хотя ключ ресурса должен быть уникальным в пределах каждого отдельного словаря, один и тот же ключ может встречаться несколько раз в наборе объединенных словарей. В этом случае возвращаемый ресурс будет поступать из последнего словаря, последовательно найденного в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекции. Если коллекция была определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], порядок объединенных словарей в коллекции — это порядок элементов, указанный в разметке. <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Если ключ определен в главном словаре, а также в словаре, который был объединен, возвращаемый ресурс поступит из основного словаря. Эти правила поиска применяются одинаково для ссылок как на статические, так и на динамические ресурсы.  
  
### <a name="merged-dictionaries-and-code"></a>Объединенные словари и код  
 Объединенные словари могут быть добавлены в словарь `Resources` с помощью кода. Изначально пустое <xref:System.Windows.ResourceDictionary> значение по умолчанию, которое `Resources` существует для любого свойства, также имеет изначально <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> пустое свойство коллекции по умолчанию. Чтобы добавить Объединенный словарь с помощью кода, можно получить <xref:System.Windows.ResourceDictionary>ссылку на требуемый Первичный объект, получить значение его <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> свойства и `Add` вызвать для универсального `Collection` типа, содержащегося в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Добавляемый объект должен быть новым <xref:System.Windows.ResourceDictionary>. В коде <xref:System.Windows.ResourceDictionary.Source%2A> свойство не задается. Вместо этого необходимо получить <xref:System.Windows.ResourceDictionary> объект, либо создав его, либо загрузив его. Один из способов <xref:System.Windows.ResourceDictionary> загрузить существующий объект для вызова <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> в существующем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файловом потоке <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> с <xref:System.Windows.ResourceDictionary> корнем, а затем присвоить возвращаемое значение <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URI объединенных словарей ресурсов  
 Существует несколько методов включения объединенного словаря ресурсов, указываемого форматом [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], который будет использоваться. Вообще говоря, эти методы можно разделить на две категории: ресурсы, которые компилируются как часть проекта, и ресурсы, которые не компилируются как часть проекта.  
  
 Для ресурсов, которые компилируются как часть проекта, можно использовать относительный путь, ссылающийся на расположение ресурса. Относительный путь вычисляется во время компиляции. Ресурс должен быть определен как часть проекта в качестве действия сборки ресурса. Если XAML-файл ресурса включен в проект в качестве ресурса, то не нужно копировать этот файл ресурса в выходной каталог, так как ресурс уже включен в скомпилированное приложение. Можно также использовать действие сборки содержимого, но затем будет необходимо скопировать файлы в выходной каталог и развернуть эти файлы ресурсов по тому же пути, связанному с исполняемым файлом.  
  
> [!NOTE]
> Не используйте действие сборки внедренного ресурса. Само действие сборки поддерживается для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений, но <xref:System.Windows.ResourceDictionary.Source%2A> разрешение не включает <xref:System.Resources.ResourceManager>и, таким способом, не может разделять отдельные ресурсы из потока. Внедренный ресурс по-прежнему можно использовать для других целей, пока вы также <xref:System.Resources.ResourceManager> используете для доступа к ресурсам.  
  
 Близким методом являются использование URI типа pack в файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и ссылка на него в качестве источника. URI типа pack позволяет ссылки на компоненты связанных сборок и другие методы. Дополнительные сведения об URI типа pack см. в разделе [Ресурсы, контент и файлы данных приложения WPF](../app-development/wpf-application-resource-content-and-data-files.md).  
  
 Для ресурсов, которые не компилируются как часть проекта, URI вычисляется во время выполнения. Для ссылки на файл ресурсов можно использовать общий транспорт URI, такой как file: или http:. Недостаток подхода с использованием некомпилированного ресурса заключается в том, что для доступа file: требуются дополнительные действия по развертыванию, а доступ http: подразумевает зону безопасности Интернета.  
  
### <a name="reusing-merged-dictionaries"></a>Многократное использование объединенных словарей  
 Вы можете многократно или совместно использовать объединенные словари ресурсов в приложениях, поскольку на словарь ресурсов, предназначенный для слияния, можно ссылаться через любые допустимые [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Точный способ сделать это будет зависеть от стратегии развертывания приложения и используемой модели приложения. Вышеупомянутая стратегия URI типа pack обеспечивает способ совместного создания объединенного ресурса между несколькими проектами в процессе разработки путем совместного использования ссылки на сборку. В этом сценарии ресурсы по-прежнему распространяются клиентом и по крайней мере одно из приложений должно разворачивать связанную сборку. Можно также ссылаться на объединенные ресурсы с помощью распределенного URI, который использует протокол http.  
  
 Запись объединенных словарей как локальных файлов приложения или в локальное общее хранилище является другим возможным сценарием объединенного словаря или развертывания приложения.  
  
### <a name="localization"></a>Локализация  
 Если ресурсы, которые необходимо локализовать, изолированы от словарей, объединенных в основные словари, и хранятся как свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], эти файлы можно локализовать отдельно. Этот способ является упрощенной альтернативой для локализации вспомогательных сборок ресурсов. Дополнительные сведения см. в статье [Общие сведения о глобализации и локализации WPF](wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.ResourceDictionary>
- [Ресурсы XAML](xaml-resources.md)
- [Ресурсы и код](resources-and-code.md)
- [Файлы ресурсов, содержимого и данных WPF-приложения](../app-development/wpf-application-resource-content-and-data-files.md)
