---
title: Атрибут x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459925"
---
# <a name="xshared-attribute"></a>Атрибут x:Shared
Если задано значение `false`, изменяет поведение извлечения ресурсов WPF, чтобы запросы к ресурсу с атрибутами создали новый экземпляр для каждого запроса вместо того, чтобы совместно использовать один и тот же экземпляр для всех запросов.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Заметки  
 `x:Shared` сопоставляется с пространством имен XAML языка XAML и распознается как допустимый элемент языка XAML путем .NET Framework служб XAML и его средств чтения XAML. Однако указанные возможности `x:Shared` применимы только для приложений WPF и средства синтаксического анализа XAML WPF. В WPF `x:Shared` используется только в качестве атрибута, если он применяется к объекту, существующему в <xref:System.Windows.ResourceDictionary>WPF. Другие случаи использования не вызывают исключений синтаксического анализа или других ошибок, но не оказывают никакого влияния.  
  
 Значение `x:Shared` не указано в спецификации языка XAML. Другие реализации XAML, например сборки, основанные на .NET Framework службах XAML, не обязательно предоставляют поддержку общего доступа к ресурсам. Такие реализации XAML могут обеспечить аналогичное поведение в поддерживающей платформе, которая также используется `x:Shared` значений.  
  
 В WPF условием `x:Shared` по умолчанию для ресурсов является `true`. Это условие означает, что любой заданный запрос ресурса всегда возвращает один и тот же экземпляр.  
  
 Изменение объекта, возвращаемого через API ресурсов, например <xref:System.Windows.FrameworkElement.FindResource%2A>или изменение объекта непосредственно в <xref:System.Windows.ResourceDictionary>, изменяет исходный ресурс. Если ссылки на этот ресурс были динамическими ссылками на ресурсы, потребители этого ресурса получают измененный ресурс.  
  
 Если ссылки на ресурс были ссылками на статические ресурсы, изменения ресурса после [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] времени обработки несущественны. Дополнительные сведения о статических и динамических ссылках на ресурс см. в разделе [ресурсы XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Явное указание `x:Shared="true"` выполняется редко, так как это значение уже используется по умолчанию. Прямой эквивалент кода для `x:Shared` в объектной модели WPF отсутствует. Он может быть указан только в использовании XAML и должен обрабатываться либо поведением WPF по умолчанию, либо в промежуточном потоке узлов XAML по пути загрузки, если он обрабатывается с помощью .NET Framework служб XAML и его средств чтения XAML.  
  
 Сценарий для `x:Shared="false"` заключается в том, что в качестве ресурса определяется <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> производный класс, а затем в модель содержимого вводится ресурс элемента. `x:Shared="false"` позволяет вводить ресурс элемента несколько раз в одной коллекции (например, <xref:System.Windows.Controls.UIElementCollection>). Без `x:Shared="false"` это недопустимо, так как коллекция обеспечивает уникальность ее содержимого. Однако `x:Shared="false"` поведение создает еще один идентичный экземпляр ресурса вместо того, чтобы возвращать тот же экземпляр.  
  
 Другой сценарий для `x:Shared="false"` — если для значений анимации используется ресурс <xref:System.Windows.Freezable>, но требуется изменить ресурс на основе анимации.  
  
 Обработка строк `false` не учитывает регистр.  
  
 В WPF `x:Shared` допустимы только при следующих условиях:  
  
- <xref:System.Windows.ResourceDictionary>, содержащий элементы с `x:Shared`, должны быть скомпилированы. <xref:System.Windows.ResourceDictionary> не может находиться в свободном XAML или использоваться для тем.  
  
- <xref:System.Windows.ResourceDictionary>, содержащие элементы, не должны быть вложены в другой <xref:System.Windows.ResourceDictionary>. Например, нельзя использовать `x:Shared` для элементов в <xref:System.Windows.ResourceDictionary>, находящихся в <xref:System.Windows.Style>, который уже является элементом <xref:System.Windows.ResourceDictionary>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.ResourceDictionary>
- [Ресурсы XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Базовые элементы](../wpf/advanced/base-elements.md)
