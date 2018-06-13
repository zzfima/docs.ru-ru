---
title: Сериализация ограничений XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: cbe8d517b8794f6aae7190457a077422d235acb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547967"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Сериализация ограничений XamlWriter.Save
[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> Можно использовать для сериализации содержимого [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложение как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла. Однако существуют некоторые заметные ограничения в том, что именно подлежит сериализации. В данном разделе описаны эти ограничения и некоторые общие рекомендации.  
  
 
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Представление во время выполнения, а не во время разработки  
 Основные философии, что можно сериализовать с помощью вызова <xref:System.Windows.Markup.XamlWriter.Save%2A> , результат будет представление объект сериализуется во время выполнения. Многие свойства разработки исходного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла могут уже оптимизирован или потерян по времени, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] загружается как объекты в памяти и не сохраняются при вызове <xref:System.Windows.Markup.XamlWriter.Save%2A> для сериализации. Результат сериализации — эффективное представление построенного логического дерева приложения, но не обязательно исходного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который его создал. Эти проблемы затрудняют для использования <xref:System.Windows.Markup.XamlWriter.Save%2A> сериализации как часть обширным [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] область конструктора.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>Сериализация самодостаточна  
 Сериализованные выходные данные <xref:System.Windows.Markup.XamlWriter.Save%2A> является автономной; все, что сериализуется содержится внутри [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] одной странице, с помощью одного корневого элемента и нет внешних ссылок, кроме [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]. Например, если страницы ссылаются на ресурсы из ресурсов приложения, они будут отображаться, как если бы они были компонентом сериализуемой страницы.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Ссылки на расширения разыменовываются  
 Общие ссылки на объекты, сделанные различными форматами расширения разметки, такие как `StaticResource` или `Binding`, будут разыменованы в процессе сериализации. Они уже были разыменован во время выполнения приложения, созданных объектов в памяти и <xref:System.Windows.Markup.XamlWriter.Save%2A> логику повторно не посещает исходный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для восстановления таких ссылок для сериализованных выходных данных. Это потенциально замораживает любое значение, полученное из привязки данных или ресурсов, которое в последний раз использовалось представлением во время выполнения, и остается только ограниченная или косвенная возможность отличать такое значение от любого другого значения, установленного локально. Образы сериализуются как ссылки объектов на изображения в том виде, в котором они существуют в проекте, а не как исходные ссылки на источники, теряя изначально указанные ссылками имя файла или [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Ресурсы, объявленные на одной странице, воспринимаются как сериализованные в том месте, где они были указаны ссылками, а не сохраняются как ключ коллекции ресурсов.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>Обработка событий не сохраняется  
 Если обработчики событий, которые добавляются с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], будут сериализованы, то они не сохранятся. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] без кода программной части (и без связанного механизма x:Code) не имеет возможности сериализовать процедурную логику времени выполнения. Поскольку сериализация является самодостаточной и ограничивается логическим деревом, не существует средств для хранения обработчиков событий. В результате атрибуты обработчика событий (и атрибут, и строковое значение имени обработчика) удаляются из выходных данных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Реалистичные сценарии использования XAMLWriter.Save  
 Хотя ограничения, перечисленные ниже, является достаточно значительными, по-прежнему существует несколько соответствующих сценариев использования <xref:System.Windows.Markup.XamlWriter.Save%2A> для сериализации.  
  
-   Вывод векторных или графических данных. Вывод преобразованной для просмотра области можно использовать для воспроизведения того же вектора или графики при перезагрузке.  
  
-   Форматированный текст и потоковые документы. Текст и все форматирование элементов и элементы внутри него сохраняются в выходных данных. Это может быть полезно для механизмов, которые аппроксимируют функциональность буфера обмена.  
  
-   Сохранение данных бизнес-объекта. При сохранении данных в пользовательских элементах, например данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], при условии, что бизнес-объекты соответствуют базовым правилам [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], таким как предоставление настраиваемых конструкторов и преобразование значений свойств по ссылке, эти бизнес-объекты могут быть сохранены посредством сериализации.
