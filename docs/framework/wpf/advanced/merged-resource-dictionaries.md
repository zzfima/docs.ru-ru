---
title: "Объединенные словари ресурсов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ce02b772bacf2115a1bb74039fdff30a46fea8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="merged-resource-dictionaries"></a>Объединенные словари ресурсов
Ресурсы [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поддерживают функцию объединенных словарей ресурсов. Эта функция обеспечивает способ определения части ресурсов приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] за пределами скомпилированного приложения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Затем ресурсы можно совместно использовать в приложениях; они также более удобно изолируются для локализации.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Общие сведения об объединенном словаре ресурсов  
 Для представления на странице объединенного словаря ресурсов используйте в разметке следующий синтаксис.  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Обратите внимание, что <xref:System.Windows.ResourceDictionary> элемент не имеет [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md), что обычно требуется для всех элементов в коллекции ресурсов. Другая <xref:System.Windows.ResourceDictionary> ссылка в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекции является особым случаем, зарезервированных для этого скрипта объединенного словаря ресурсов. <xref:System.Windows.ResourceDictionary> Представляющий объединенный словарь ресурсов не может иметь [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md). Как правило, каждый <xref:System.Windows.ResourceDictionary> в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> указывает коллекцию <xref:System.Windows.ResourceDictionary.Source%2A> атрибута. Значение <xref:System.Windows.ResourceDictionary.Source%2A> должно быть [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] , разрешает путь к файлу ресурсов для слияния. Местом назначения этого [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] должен быть другой [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла, с <xref:System.Windows.ResourceDictionary> качестве корневого элемента.  
  
> [!NOTE]
>  Допустим, для определения ресурсов в <xref:System.Windows.ResourceDictionary> , который указан как объединенный словарь, либо в качестве альтернативы указание <xref:System.Windows.ResourceDictionary.Source%2A>, или в дополнение к включаются любые ресурсы из указанного источника. Однако это не очень распространенный сценарий; основным сценарием для объединенных словарей является объединение ресурсов из внешних файлов. Если вы хотите указать ресурсы внутри разметки страницы, обычно следует определить их в главном <xref:System.Windows.ResourceDictionary> , а не в объединенных словарей.  
  
## <a name="merged-dictionary-behavior"></a>Поведение объединенного словаря  
 Ресурсы в объединенном словаре занимают место в области поиска ресурсов сразу после области главного словаря ресурсов, в который они будут включены. Хотя ключ ресурса должен быть уникальным в пределах каждого отдельного словаря, один и тот же ключ может встречаться несколько раз в наборе объединенных словарей. В этом случае будет получен ресурс, который возвращается из последнего словаря, последовательно найденного в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекции. Если <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> коллекции был определен в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], то порядок объединенных словарей в коллекции является порядок элементов, как указано в разметке. Если ключ определен в главном словаре, а также в словаре, который был объединен, возвращаемый ресурс поступит из основного словаря. Эти правила поиска применяются одинаково для ссылок как на статические, так и на динамические ресурсы.  
  
### <a name="merged-dictionaries-and-code"></a>Объединенные словари и код  
 Объединенные словари могут быть добавлены в словарь `Resources` с помощью кода. Значение по умолчанию, изначально пуста <xref:System.Windows.ResourceDictionary> , существует для `Resources` свойство также имеет значение по умолчанию, изначально пуста <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> свойства коллекции. Чтобы добавить объединенный словарь с помощью кода, можно получить ссылку на нужный источник <xref:System.Windows.ResourceDictionary>, получить его <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> значение свойства и вызов `Add` универсального `Collection` , содержащихся в <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Добавляемый объект должен быть новый <xref:System.Windows.ResourceDictionary>. В коде, не задано <xref:System.Windows.ResourceDictionary.Source%2A> свойство. Вместо этого необходимо получить <xref:System.Windows.ResourceDictionary> , создание или загрузка один объект. Один из способов загрузки существующего <xref:System.Windows.ResourceDictionary> для вызова <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> на существующем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлового потока, который имеет <xref:System.Windows.ResourceDictionary> корень, затем приведение <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> возвращаемое значение для <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URI объединенных словарей ресурсов  
 Существует несколько методов включения объединенного словаря ресурсов, указываемого форматом [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], который будет использоваться. Вообще говоря, эти методы можно разделить на две категории: ресурсы, которые компилируются как часть проекта, и ресурсы, которые не компилируются как часть проекта.  
  
 Для ресурсов, которые компилируются как часть проекта, можно использовать относительный путь, ссылающийся на расположение ресурса. Относительный путь вычисляется во время компиляции. Ресурс должен быть определен как часть проекта в качестве действия сборки ресурса. Если XAML-файл ресурса включен в проект в качестве ресурса, то не нужно копировать этот файл ресурса в выходной каталог, так как ресурс уже включен в скомпилированное приложение. Можно также использовать действие сборки содержимого, но затем будет необходимо скопировать файлы в выходной каталог и развернуть эти файлы ресурсов по тому же пути, связанному с исполняемым файлом.  
  
> [!NOTE]
>  Не используйте действие сборки внедренного ресурса. Само действие построения поддерживается для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения, но разрешения <xref:System.Windows.ResourceDictionary.Source%2A> не включают <xref:System.Resources.ResourceManager>и таким образом, невозможно разделить отдельных ресурсов из потока. Внедренный ресурс по-прежнему можно использовать для других целей при условии, что также используется <xref:System.Resources.ResourceManager> доступ к ресурсам.  
  
 Близким методом являются использование URI типа pack в файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и ссылка на него в качестве источника. URI типа pack позволяет ссылки на компоненты связанных сборок и другие методы. Дополнительные сведения об URI типа pack см. в разделе [Ресурсы, контент и файлы данных приложения WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Для ресурсов, которые не компилируются как часть проекта, URI вычисляется во время выполнения. Для ссылки на файл ресурсов можно использовать общий транспорт URI, такой как file: или http:. Недостаток подхода с использованием некомпилированного ресурса заключается в том, что для доступа file: требуются дополнительные действия по развертыванию, а доступ http: подразумевает зону безопасности Интернета.  
  
### <a name="reusing-merged-dictionaries"></a>Многократное использование объединенных словарей  
 Вы можете многократно или совместно использовать объединенные словари ресурсов в приложениях, поскольку на словарь ресурсов, предназначенный для слияния, можно ссылаться через любые допустимые [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Точный способ сделать это будет зависеть от стратегии развертывания приложения и используемой модели приложения. Вышеупомянутая стратегия URI типа pack обеспечивает способ совместного создания объединенного ресурса между несколькими проектами в процессе разработки путем совместного использования ссылки на сборку. В этом сценарии ресурсы по-прежнему распространяются клиентом и по крайней мере одно из приложений должно разворачивать связанную сборку. Можно также ссылаться на объединенные ресурсы с помощью распределенного URI, который использует протокол http.  
  
 Запись объединенных словарей как локальных файлов приложения или в локальное общее хранилище является другим возможным сценарием объединенного словаря или развертывания приложения.  
  
### <a name="localization"></a>Локализация  
 Если ресурсы, которые необходимо локализовать, изолированы от словарей, объединенных в основные словари, и хранятся как свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], эти файлы можно локализовать отдельно. Этот способ является упрощенной альтернативой для локализации вспомогательных сборок ресурсов. Дополнительные сведения см. в статье [Общие сведения о глобализации и локализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.ResourceDictionary>  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [Файлы ресурсов, содержимого и данных WPF-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
