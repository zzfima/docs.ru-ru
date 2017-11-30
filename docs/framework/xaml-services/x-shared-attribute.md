---
title: "Атрибут x:Shared"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d6a9333b2267e82fc25b2a0ec4bf5dd14f644078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xshared-attribute"></a>Атрибут x:Shared
Если задано значение `false`, изменяет поведение извлечения ресурсов WPF, чтобы запросы ресурсу с атрибутом создают новый экземпляр для каждого запроса, а не один и тот же экземпляр для всех запросов.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Примечания  
 `x:Shared`сопоставлен с пространством имен XAML языка XAML и распознается как допустимый элемент языка XAML служб XAML .NET Framework и ее средства чтения XAML. Однако указанные возможности `x:Shared` относятся только для приложений WPF и средство синтаксического анализа XAML в WPF. В WPF `x:Shared` полезен только как атрибут применительно к объект, который существует в WPF <xref:System.Windows.ResourceDictionary>. Другие варианты использования не создают исключения синтаксического анализа или других ошибок, но они не оказывают влияния.  
  
 Значение `x:Shared` не указано в спецификации языка XAML. Другие реализации XAML, например те, основанных на службах XAML .NET Framework не обязательно поддерживают совместное использование ресурсов. Такие реализации XAML могут предоставлять подобное поведение во вспомогательной платформе, который также используется `x:Shared` значения.  
  
 В WPF, значение по умолчанию `x:Shared` условие для ресурсов `true`. Это состояние означает, что все запросы к данному ресурсу всегда возвращает тот же экземпляр.  
  
 Объект, который возвращается с помощью ресурсов API-интерфейса, такие как изменение <xref:System.Windows.FrameworkElement.FindResource%2A>, или изменении объекта непосредственно в <xref:System.Windows.ResourceDictionary>, изменяется исходный ресурс. Если ссылки на этот ресурс были динамическими, потребители этого ресурса получение измененных ресурсов.  
  
 Если ссылки на ресурс были статическими, изменения ресурса после [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] время обработки неприменимы. Дополнительные сведения о статических и ссылок на динамический ресурс см. в разделе [ресурсов XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Явное указание `x:Shared="true"` делается редко, так как он уже имеет значение по умолчанию. Нет эквивалента для прямого кода `x:Shared` в WPF объектной модели; он может быть указан только при использовании XAML и должны обрабатываться с помощью WPF поведения по умолчанию или в промежуточном потоке узлов XAML в пути загрузки при обработке с помощью .NET Framework XAML Se служб и его средства чтения XAML.  
  
 Сценарии для `x:Shared="false"` — Если вы определяете <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> производного класса в качестве ресурса, а затем вводите ресурсов элемента в модели содержимого. `x:Shared="false"`включает элемент ресурс должен быть представлен несколько раз в одной коллекции (например, <xref:System.Windows.Controls.UIElementCollection>). Без `x:Shared="false"` это недопустимо, поскольку коллекция обеспечивает уникальность ее содержимого. Тем не менее `x:Shared="false"` поведение создает другой идентичный экземпляр ресурса, а не возвращает тот же экземпляр.  
  
 Другим случаем `x:Shared="false"` при использовании <xref:System.Windows.Freezable> ресурсов для значений анимации, но требуется изменить ресурса для каждой анимации.  
  
 При обработке строки `false` регистр не учитывается.  
  
 В WPF `x:Shared` допустим только при следующих условиях:  
  
-   <xref:System.Windows.ResourceDictionary> , Содержащий элементы с `x:Shared` должен быть скомпилирован. <xref:System.Windows.ResourceDictionary> Не может быть в пределах Свободный XAML, или для темы.  
  
-   <xref:System.Windows.ResourceDictionary> , Содержащий элементы не должен быть вложен в другой <xref:System.Windows.ResourceDictionary>. Например, нельзя использовать `x:Shared` для элементов в <xref:System.Windows.ResourceDictionary> , находится в пределах <xref:System.Windows.Style> , уже <xref:System.Windows.ResourceDictionary> элемента.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.ResourceDictionary>  
 [Ресурсы XAML](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Базовые элементы](../../../docs/framework/wpf/advanced/base-elements.md)
