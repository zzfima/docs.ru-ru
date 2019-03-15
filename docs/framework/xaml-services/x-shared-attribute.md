---
title: Атрибут x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: 42de341d59e3e70103db765faf3160b5fe3250d3
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58039403"
---
# <a name="xshared-attribute"></a>Атрибут x:Shared
Если задано значение `false`, изменяет поведение извлечения ресурсов WPF, чтобы запросы с атрибутами ресурсов создают новый экземпляр для каждого запроса, а не один и тот же экземпляр для всех запросов.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Примечания  
 `x:Shared` сопоставляется с пространством имен XAML языка XAML и распознается как допустимый элемент языка XAML служб XAML .NET Framework и ее средства чтения XAML. Тем не менее указанные возможности `x:Shared` относятся только для приложений WPF и средство синтаксического анализа XAML WPF. В WPF `x:Shared` полезен только как атрибут при применении к объекту, который существует в WPF <xref:System.Windows.ResourceDictionary>. Другие данные об использовании не вызывают исключения синтаксического анализа или других ошибок, но он не оказывает влияния.  
  
 Значение `x:Shared` не указано в спецификации языка XAML. Другие реализации XAML, например те, которые зависят от служб XAML .NET Framework, не обязательно предоставляют общий доступ к ресурсам поддержки. Такие реализации XAML могут предоставлять подобное поведение в вспомогательные framework, которая также используется `x:Shared` значения.  
  
 В WPF, значение по умолчанию `x:Shared` условий для ресурсов является `true`. Это условие означает, что все запросы к данному ресурсу всегда возвращает тот же экземпляр.  
  
 Изменение объекта, который возвращается через API, ресурс, такие как <xref:System.Windows.FrameworkElement.FindResource%2A>, или изменении объекта непосредственно в <xref:System.Windows.ResourceDictionary>, изменяет исходный ресурс. Если ссылки на этот ресурс были ссылки на динамические ресурсы, потребители этого ресурса получение измененных ресурсов.  
  
 Если ссылки на ресурс были статическими, изменения ресурса после [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] актуальны ли время обработки. Дополнительные сведения о статических и ссылки на динамические ресурсы, см. в разделе [ресурсы XAML](../wpf/advanced/xaml-resources.md).  
  
 Явно указав `x:Shared="true"` делается редко, так как он уже имеет значение по умолчанию. Нет эквивалента для прямого кода `x:Shared` в WPF объектной модели; он может указываться только при использовании XAML и должны быть обработаны с WPF по умолчанию или в промежуточный поток узлов XAML в пути загрузки при обработке с помощью .NET Framework XAML Se служб и его средства чтения XAML.  
  
 Сценарий для `x:Shared="false"` Если вы определяете <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> производного класса как ресурс и затем вводят ресурсов элемент в модели содержимого. `x:Shared="false"` включает ресурс элемент должен быть представлен несколько раз в одной коллекции (например, <xref:System.Windows.Controls.UIElementCollection>). Без `x:Shared="false"` это недопустимо, поскольку коллекция обеспечивает уникальность ее содержимого. Тем не менее `x:Shared="false"` поведение создает другой идентичный экземпляр ресурса, а не возвращает тот же экземпляр.  
  
 Другой сценарий для `x:Shared="false"` при использовании <xref:System.Windows.Freezable> ресурсов для значений анимации, но хотите изменить ресурса для каждой анимации.  
  
 При обработке строки `false` выполняется без учета регистра.  
  
 В WPF `x:Shared` допустим только при следующих условиях:  
  
-   <xref:System.Windows.ResourceDictionary> , Содержащая элементы с `x:Shared` должен быть скомпилирован. <xref:System.Windows.ResourceDictionary> Не может быть в пределах Свободный XAML или для темы.  
  
-   <xref:System.Windows.ResourceDictionary> , Содержащий элементы не должны быть вложены в другой <xref:System.Windows.ResourceDictionary>. Например, нельзя использовать `x:Shared` для элементов в <xref:System.Windows.ResourceDictionary> , находится в пределах <xref:System.Windows.Style> , уже <xref:System.Windows.ResourceDictionary> элемента.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.ResourceDictionary>
- [Ресурсы XAML](../wpf/advanced/xaml-resources.md)
- [Базовые элементы](../wpf/advanced/base-elements.md)
