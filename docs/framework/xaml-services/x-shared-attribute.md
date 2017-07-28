---
title: "x:Shared Attribute | Microsoft Docs"
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
  - "XAML [XAML Services], x:Shared attribute"
  - "x:Shared attribute [XAML Services]"
  - "Shared attribute in XAML [XAML Services]"
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: 16
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 16
---
# x:Shared Attribute
При установке `false` изменяется поведение поиска ресурса WPF таким образом, что запросы к ресурсу с атрибутом создают новый экземпляр для каждого запроса, а не предоставляют общий доступ к тому же экземпляру для всех запросов.  
  
## Использование атрибута XAML  
  
```  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## Заметки  
 `x:Shared` сопоставляется пространству имен XAML языка XAML и распознается как допустимый элемент языка XAML службами XAML .NET Framework и его средствами чтения XAML.  Тем не менее только указанные возможности `x:Shared` применимы к приложениям WPF и к синтаксическому анализатору WPF XAML.  В WPF `x:Shared` полезен только как атрибут при применении к объекту, который существует в WPF <xref:System.Windows.ResourceDictionary>.  Другие варианты использования не создают исключения синтаксического анализа или других ошибок, но они не имеют силы.  
  
 Значение `x:Shared` не задано в спецификации языка XAML.  Другие реализации XAML, например, созданные на основе служб XAML .NET Framework, не обязательно поддерживают совместное использование ресурсов.  Такие реализации XAML могут предоставлять подобное поведение во вспомогательной платформе, в которой также используются значения `x:Shared`.  
  
 В WPF по умолчанию условие `x:Shared` для ресурсов имеет значение `true`.  Это состояние означает, что все запросы к данному ресурсу всегда возвращают один и тот же экземпляр.  
  
 Изменение объекта, возвращаемого с помощью API ресурса, такого как <xref:System.Windows.FrameworkElement.FindResource%2A>, или изменение объекта непосредственно в <xref:System.Windows.ResourceDictionary> приводит к изменению исходного ресурса.  Если ссылки на этот ресурс были динамическими, потребители этого ресурса получат измененный ресурс.  
  
 Если ссылки на ресурс были статическими, изменения ресурса после обработки [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] не имеют значения.  Дополнительные сведения о статических и динамических ссылках на ресурсы см. в разделе [Ресурсы XAML](../../../ocs/framework/wpf/advanced/xaml-resources.md).  
  
 Явное указание `x:Shared="true"` делают редко, поскольку это значение подразумевается по умолчанию.  Отсутствует непосредственный эквивалент кода для `x:Shared` в объектной модели WPF; он может быть задан только при использовании XAML и должны быть обработан WPF\-поведением по умолчанию или в промежуточном потоке узлов XAML в пути загрузки при обработке с помощью служб XAML .NET Framework и своих модулей чтения XAML.  
  
 `x:Shared="false"` может использоваться при определении производного класса <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> в качестве ресурса и последующем вводе этого ресурса элемента в модель содержимого.  `x:Shared="false"` позволяет несколько раз вводить ресурс элемента в одну и ту же коллекцию \(например, <xref:System.Windows.Controls.UIElementCollection>\).  Без `x:Shared="false"` является недействительным, поскольку коллекция принудительно обеспечивает уникальность его содержимого.  Однако поведение `x:Shared="false"` создает другой идентичный экземпляр ресурса, а не возвращает тот же экземпляр.  
  
 Другим сценарием для `x:Shared="false"` является использование ресурса <xref:System.Windows.Freezable> для значений анимации, что требует изменения ресурса для каждой анимации.  
  
 При обработке строки `false` не учитывается регистр.  
  
 В WPF `x:Shared` является допустимым только при следующих условиях:  
  
-   Должен быть скомпилирован <xref:System.Windows.ResourceDictionary>, содержащий элементы с `x:Shared`.  <xref:System.Windows.ResourceDictionary> не может быть в пределах свободного XAML или использоваться для тем.  
  
-   <xref:System.Windows.ResourceDictionary>, содержащий элементы, не должен быть вложен в другой <xref:System.Windows.ResourceDictionary>.  Например, нельзя использовать `x:Shared` для элементов в объекте <xref:System.Windows.ResourceDictionary>, находящемся в объекте <xref:System.Windows.Style>, который уже является элементом <xref:System.Windows.ResourceDictionary>.  
  
## См. также  
 <xref:System.Windows.ResourceDictionary>   
 [Ресурсы XAML](../../../ocs/framework/wpf/advanced/xaml-resources.md)   
 [Базовые элементы](../../../ocs/framework/wpf/advanced/base-elements.md)