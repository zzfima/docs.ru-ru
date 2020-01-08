---
title: Ресурсы и код
ms.date: 03/30/2017
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
ms.openlocfilehash: 11903a9bae25b0646d944fb11038e07434996015
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559759"
---
# <a name="resources-and-code"></a>Ресурсы и код
Этот обзор посвящен преимущественно доступу к ресурсам [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и их созданию с использованием кода, а не синтаксиса [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Дополнительные сведения об общем использовании ресурсов и ресурсах с точки зрения синтаксиса [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Ресурсы XAML](xaml-resources.md).  

<a name="accessing"></a>   
## <a name="accessing-resources-from-code"></a>Доступ к ресурсам из кода  
 Ключи, идентифицирующие ресурсы, если они определены через [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также используются для извлечения определенных ресурсов при запросе ресурса из кода. Самый простой способ извлечь ресурс из кода — вызвать метод <xref:System.Windows.FrameworkElement.FindResource%2A> или <xref:System.Windows.FrameworkElement.TryFindResource%2A> из объектов уровня среды в приложении. Различие между этими методами проявляется, если запрошенный ключ не найден. <xref:System.Windows.FrameworkElement.FindResource%2A> вызывает исключение; <xref:System.Windows.FrameworkElement.TryFindResource%2A> не создает исключение, но возвращает `null`. Каждый из этих методов принимает ключ ресурса в качестве входного параметра и возвращает объект со слабой типизацией. Как правило, ключ ресурса является строкой, но иногда используются и нестроковые ключи. Подробнее см. в разделе [Использование объектов в качестве ключей](#objectaskey). Как правило, возвращаемый объект приводится к типу, необходимому для свойства, которое устанавливается при запросе ресурса. Логика поиска разрешения ресурса кода такая же, как и в случае динамической ссылки на ресурс [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Поиск ресурсов начинается с вызывающего элемента, затем продолжается в последовательных родительских элементах в логическом дереве. При необходимости поиск продолжается в ресурсах приложений, темах и системных ресурсах. Запрос кода для ресурса будет правильно учитывать изменения во время выполнения в словарях ресурсов, которые могли быть сделаны после загрузки данного словаря из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а также изменения системных ресурсов в реальном времени.  
  
 Ниже приведен краткий пример кода, который находит ресурс по ключу и использует возвращенное значение для задания свойства, реализованного в виде <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчика событий.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Альтернативный способ назначения ссылки на ресурс — <xref:System.Windows.FrameworkElement.SetResourceReference%2A>. Этот метод принимает два параметра — ключ ресурса и идентификатор конкретного свойства зависимостей из экземпляра элемента, которому должно быть присвоено значение ресурса. Функционально этот метод аналогичен, но имеет преимущество в том плане, что не требует приведения возвращаемых значений.  
  
 Еще один способ программного доступа к ресурсам — доступ к содержимому свойства <xref:System.Windows.FrameworkElement.Resources%2A> в виде словаря. Доступ к словарю, содержащемуся в этом свойстве, включает добавление новых ресурсов в существующие коллекции, проверку оригинальности имени ключа в коллекции, а также другие операции со словарем/коллекцией. При написании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения полностью в коде можно также создать всю коллекцию в коде, присвоить ей ключи, а затем назначить завершенную коллекцию свойству <xref:System.Windows.FrameworkElement.Resources%2A> установленного элемента. Это будет описано в следующем разделе.  
  
 Вы можете индексировать в любой заданной <xref:System.Windows.FrameworkElement.Resources%2A> коллекции, используя конкретный ключ в качестве индекса, но следует помнить, что доступ к ресурсу таким способом не соответствует обычным правилам среды выполнения для разрешения ресурсов. У вас будет только доступ к этой конкретной коллекции. Поиск ресурсов не будет пересекать область действия корня или приложения, если в запрашиваемом ключе не найден действительный объект. Тем не менее в некоторых случаях этот подход может иметь преимущество в производительности, поскольку область поиска ключа более ограничена. Дополнительные сведения о работе с словарем ресурсов непосредственно см. в разделе <xref:System.Windows.ResourceDictionary> класс.  
  
<a name="creating"></a>   
## <a name="creating-resources-with-code"></a>Создание ресурсов с помощью кода  
 Пи создании приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] полностью в коде может также понадобиться создать в коде все ресурсы в этом приложении. Чтобы добиться этого, создайте новый экземпляр <xref:System.Windows.ResourceDictionary>, а затем добавьте все ресурсы в словарь, используя последовательные вызовы для <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>. Затем используйте созданную <xref:System.Windows.ResourceDictionary>, чтобы задать свойство <xref:System.Windows.FrameworkElement.Resources%2A> для элемента, который находится в области страницы, или <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>. Можно также поддерживать <xref:System.Windows.ResourceDictionary> как автономный объект, не добавляя его в элемент. Однако в этом случае для доступа к ресурсам внутри него потребуется ключ элемента, как для общего словаря. <xref:System.Windows.ResourceDictionary>, который не присоединен к элементу `Resources` свойство не будет существовать как часть дерева элементов и не имеет области в последовательности поиска, которая может использоваться <xref:System.Windows.FrameworkElement.FindResource%2A> и связанными методами.  
  
<a name="objectaskey"></a>   
## <a name="using-objects-as-keys"></a>Использование объектов в качестве ключей  
 В большинстве случаев использования ресурса ключ ресурса устанавливается в виде строки. Однако различные функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] намеренно не используют строковый тип для указания ключей, вместо этого параметр является объектом. Возможность доступа объекта к ресурсу по ключу используется в поддержке стилей и тем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Стили в темах, которые становятся стилем по умолчанию для элемента управления, не относящегося к стилю, имеют каждый из ключевых <xref:System.Type> элемента управления, к которому они должны применяться. Ввод с помощью ключа по типу обеспечивает надежный механизм поиска, который работает со стандартными экземплярами каждого типа элемента управления, а тип может быть обнаружен отражением и использоваться для создания стилей производных классов, даже если у производного типа нет стиля по умолчанию. Вы можете указать <xref:System.Type> ключ для ресурса, определенного в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], с помощью [расширения разметки x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md). Аналогичные расширения существуют для других случаев использования нестрокового ключа, поддерживающих функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как [Расширение разметки ComponentResourceKey](componentresourcekey-markup-extension.md).  
  
## <a name="see-also"></a>См. также:

- [Ресурсы XAML](xaml-resources.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
