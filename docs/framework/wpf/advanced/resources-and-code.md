---
title: "Ресурсы и код"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys [WPF], using objects as
- resources [WPF], accessing from procedural code
- procedural code [WPF], creating resources with
- procedural code [WPF], accessing resources from
- resources [WPF], creating with procedural code
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 772c44b63627204da7056a5707f2840a82053f11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="resources-and-code"></a>Ресурсы и код
Этот обзор посвящен преимущественно доступу к ресурсам [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и их созданию с использованием кода, а не синтаксиса [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Дополнительные сведения об общем использовании ресурсов и ресурсах с точки зрения синтаксиса [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
  
  
<a name="accessing"></a>   
## <a name="accessing-resources-from-code"></a>Доступ к ресурсам из кода  
 Ключи, идентифицирующие ресурсы, если они определены через [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также используются для извлечения определенных ресурсов при запросе ресурса из кода. Самый простой способ извлечения ресурсов с помощью кода является вызов либо <xref:System.Windows.FrameworkElement.FindResource%2A> или <xref:System.Windows.FrameworkElement.TryFindResource%2A> метода из объектов уровня структуры в приложении. Различие между этими методами проявляется, если запрошенный ключ не найден. <xref:System.Windows.FrameworkElement.FindResource%2A>вызывает исключение. <xref:System.Windows.FrameworkElement.TryFindResource%2A> не вызовут исключения, но она возвращает `null`. Каждый из этих методов принимает ключ ресурса в качестве входного параметра и возвращает объект со слабой типизацией. Как правило, ключ ресурса является строкой, но иногда используются и нестроковые ключи. Подробнее см. в разделе [Использование объектов в качестве ключей](#objectaskey). Как правило, возвращаемый объект приводится к типу, необходимому для свойства, которое устанавливается при запросе ресурса. Логика поиска разрешения ресурса кода такая же, как и в случае динамической ссылки на ресурс [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Поиск ресурсов начинается с вызывающего элемента, затем продолжается в последовательных родительских элементах в логическом дереве. При необходимости поиск продолжается в ресурсах приложений, темах и системных ресурсах. Запрос кода для ресурса будет правильно учитывать изменения во время выполнения в словарях ресурсов, которые могли быть сделаны после загрузки данного словаря из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а также изменения системных ресурсов в реальном времени.  
  
 Ниже приведен пример кода, который находит ресурс по ключу и возвращенное значение используется для задания свойства, реализованы в виде <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчика событий.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Альтернативный метод для назначения ссылку на ресурс является <xref:System.Windows.FrameworkElement.SetResourceReference%2A>. Этот метод принимает два параметра — ключ ресурса и идентификатор конкретного свойства зависимостей из экземпляра элемента, которому должно быть присвоено значение ресурса. Функционально этот метод аналогичен, но имеет преимущество в том плане, что не требует приведения возвращаемых значений.  
  
 Другой способ программного доступа к ресурсам — доступ к содержимому <xref:System.Windows.FrameworkElement.Resources%2A> свойство как словарь. Доступ к словарю, содержащемуся в этом свойстве, включает добавление новых ресурсов в существующие коллекции, проверку оригинальности имени ключа в коллекции, а также другие операции со словарем/коллекцией. При создании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения полностью в коде можно также создать всю коллекцию в коде, назначьте ему ключей и затем присвоить завершенную коллекцию <xref:System.Windows.FrameworkElement.Resources%2A> свойство установленного элемента. Это будет описано в следующем разделе.  
  
 Можно индексировать в любой заданной <xref:System.Windows.FrameworkElement.Resources%2A> коллекции, используя определенный ключ в качестве индекса, но следует иметь в виду, что доступ к ресурсу таким образом не соответствует правилам обычного выполнения разрешения ресурсов. У вас будет только доступ к этой конкретной коллекции. Поиск ресурсов не будет пересекать область действия корня или приложения, если в запрашиваемом ключе не найден действительный объект. Тем не менее в некоторых случаях этот подход может иметь преимущество в производительности, поскольку область поиска ключа более ограничена. В разделе <xref:System.Windows.ResourceDictionary> Дополнительные сведения о том, как работать со словарем ресурсов напрямую.  
  
<a name="creating"></a>   
## <a name="creating-resources-with-code"></a>Создание ресурсов с помощью кода  
 Пи создании приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] полностью в коде может также понадобиться создать в коде все ресурсы в этом приложении. Чтобы добиться этого, создайте новый <xref:System.Windows.ResourceDictionary> экземпляра, а затем добавьте все ресурсы в словарь с помощью последовательных вызовов <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>. Затем с помощью <xref:System.Windows.ResourceDictionary> созданный таким образом, чтобы задать <xref:System.Windows.FrameworkElement.Resources%2A> свойство элемента, который присутствует в области страницы, или <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>. Можно также хранить <xref:System.Windows.ResourceDictionary> как автономный объект без добавления элемента. Однако в этом случае для доступа к ресурсам внутри него потребуется ключ элемента, как для общего словаря. Объект <xref:System.Windows.ResourceDictionary> , не присоединенные к элементу `Resources` свойство не будет существовать как часть дерева элементов и не будет иметь область в последовательности поиска, которая может использоваться <xref:System.Windows.FrameworkElement.FindResource%2A> и соответствующими методами.  
  
<a name="objectaskey"></a>   
## <a name="using-objects-as-keys"></a>Использование объектов в качестве ключей  
 В большинстве случаев использования ресурса ключ ресурса устанавливается в виде строки. Однако различные функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] намеренно не используют строковый тип для указания ключей, вместо этого параметр является объектом. Возможность доступа объекта к ресурсу по ключу используется в поддержке стилей и тем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Стили в темах, которые становятся стилем по умолчанию для элемента управления не стиля по ключу с <xref:System.Type> элемента управления, которому они применяются. Ввод с помощью ключа по типу обеспечивает надежный механизм поиска, который работает со стандартными экземплярами каждого типа элемента управления, а тип может быть обнаружен отражением и использоваться для создания стилей производных классов, даже если у производного типа нет стиля по умолчанию. Можно указать <xref:System.Type> ключа для ресурса, определенного в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с помощью [расширение разметки x: Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Аналогичные расширения существуют для других случаев использования нестрокового ключа, поддерживающих функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как [Расширение разметки ComponentResourceKey](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).  
  
## <a name="see-also"></a>См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
