---
title: "Расширение разметки ThemeDictionary | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ThemeDictionaryExtension"
  - "ThemeDictionary"
helpviewer_keywords: 
  - "ThemeDictionary - расширение разметки"
  - "XAML, ThemeDictionary - расширение разметки"
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Расширение разметки ThemeDictionary
Предоставляет для авторов пользовательского элемента управления или приложений, которые объединяют элементы управления сторонних производителей, способ загрузки определенных темой словарей ресурсов для использования в стилизации элемента управления.  
  
## Использование атрибута XAML  
  
```  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## Использование элемента объекта XAML  
  
```  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`assemblyUri`|Сборка [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], содержащая сведения темы.  Как правило, это пакет URI, который ссылается на сборку в большом пакете.  Сборка ресурсов и пакет URI упрощают развертывание.  Дополнительные сведения см. в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).|  
  
## Заметки  
 Это расширение предназначено для заполнения только одного значения конкретного свойства: <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=fullName>.  
  
 Используя это расширение, можно указать одну сборку ресурсов, содержащую некоторые стили для использования только при применении к пользовательской системе темы [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)], другие стили при активной теме Luna и т. д.  Используя это расширение, при необходимости содержимое словаря ресурсов элемента управления можно автоматически считать недействительным и перезагрузить для другой темы.  
  
 Строка `assemblyUri` \(значение свойства <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>\) удовлетворяет основе соглашения об именовании, определяющей, какой словарь применяется для конкретной темы.  Логика <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> для `ThemeDictionary` завершает соглашение, создавая [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], который указывает на тип словаря конкретной темы, как содержащийся внутри предварительно откомпилированной сборки ресурсов.  Описание этого соглашения или взаимодействия темы со стилизацией основных элементов управления и стилизацией уровня страницы или приложения, как концепции, полностью в данном разделе не рассматривается.  Основным скриптом использования `ThemeDictionary` является указание свойства <xref:System.Windows.ResourceDictionary.Source%2A> из `ResourceDictionary`, объявленного на уровне приложения.  При обеспечении [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для сборки через расширение `ThemeDictionary`, вместо непосредственного [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], логика расширения обеспечит логику недостоверности, которая применяется при каждом изменении системной темы.  
  
 Синтаксис атрибута является наиболее распространенным синтаксисом, который используется с этим расширением разметки.  маркер строки, указанный после идентификатора строки `ThemeDictionary`, получает значение <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> базового класса расширения <xref:System.Windows.ThemeDictionaryExtension>.  
  
 Ключевое слово `ThemeDictionary` также можно использовать в синтаксисе элемента объекта.  В этом случае указание значения свойства <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> является обязательным.  
  
 Излишним может оказаться использование `ThemeDictionary` в атрибуте, в котором свойство <xref:System.Windows.Markup.StaticExtension.Member%2A> определено как пара «свойство\=значение».  
  
```  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.  Поскольку `ThemeDictionary` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В реализации процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка данного расширения разметки определяется классом <xref:System.Windows.ThemeDictionaryExtension>.  
  
 `ThemeDictionary` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы { and } в синтаксисе их атрибутов, который является соглашением, по которому процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)