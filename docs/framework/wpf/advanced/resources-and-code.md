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
ms.openlocfilehash: 2917c9d15a6195c2d67781d6b2cfb0a5f1c136d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187170"
---
# <a name="resources-and-code"></a>Ресурсы и код
Этот обзор посвящен преимущественно доступу к ресурсам [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и их созданию с использованием кода, а не синтаксиса [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Дополнительные сведения об общем использовании ресурсов и ресурсах с точки зрения синтаксиса [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Ресурсы XAML](xaml-resources.md).  

<a name="accessing"></a>
## <a name="accessing-resources-from-code"></a>Доступ к ресурсам из кода  
 Ключи, идентифицирующие ресурсы, если они определены через [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также используются для извлечения определенных ресурсов при запросе ресурса из кода. Самый простой способ извлечь ресурс из кода <xref:System.Windows.FrameworkElement.FindResource%2A> — <xref:System.Windows.FrameworkElement.TryFindResource%2A> вызвать в приложении или метод из объектов рамочного уровня. Различие между этими методами проявляется, если запрошенный ключ не найден. <xref:System.Windows.FrameworkElement.FindResource%2A>поднимает исключение; <xref:System.Windows.FrameworkElement.TryFindResource%2A> не будет поднимать исключение, но возвращает `null`. Каждый из этих методов принимает ключ ресурса в качестве входного параметра и возвращает объект со слабой типизацией. Как правило, ключ ресурса является строкой, но иногда используются и нестроковые ключи. Подробнее см. в разделе [Использование объектов в качестве ключей](#objectaskey). Как правило, возвращаемый объект приводится к типу, необходимому для свойства, которое устанавливается при запросе ресурса. Логика поиска разрешения ресурса кода такая же, как и в случае динамической ссылки на ресурс [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Поиск ресурсов начинается с вызывающего элемента, затем продолжается в последовательных родительских элементах в логическом дереве. При необходимости поиск продолжается в ресурсах приложений, темах и системных ресурсах. Запрос кода для ресурса будет правильно учитывать изменения во время выполнения в словарях ресурсов, которые могли быть сделаны после загрузки данного словаря из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а также изменения системных ресурсов в реальном времени.  
  
 Ниже приводится краткий пример кода, который находит ресурс по ключу и <xref:System.Windows.Controls.Primitives.ButtonBase.Click> использует возвращенное значение для установки свойства, реализованного в качестве обработчика событий.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Альтернативный метод присвоения ресурсной ссылки. <xref:System.Windows.FrameworkElement.SetResourceReference%2A> Этот метод принимает два параметра — ключ ресурса и идентификатор конкретного свойства зависимостей из экземпляра элемента, которому должно быть присвоено значение ресурса. Функционально этот метод аналогичен, но имеет преимущество в том плане, что не требует приведения возвращаемых значений.  
  
 Еще один способ получить доступ к ресурсам программно <xref:System.Windows.FrameworkElement.Resources%2A> является доступ к содержимому свойства в качестве словаря. Доступ к словарю, содержащемуся в этом свойстве, включает добавление новых ресурсов в существующие коллекции, проверку оригинальности имени ключа в коллекции, а также другие операции со словарем/коллекцией. Если вы пишете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение полностью в коде, вы также можете создать всю коллекцию в коде, <xref:System.Windows.FrameworkElement.Resources%2A> назначить ключи к нему, а затем назначить готовую коллекцию в собственность установленного элемента. Это будет описано в следующем разделе.  
  
 Вы можете индексировать <xref:System.Windows.FrameworkElement.Resources%2A> в любой конкретной коллекции, используя определенный ключ в качестве индекса, но вы должны знать, что доступ к ресурсу таким образом не соответствует обычным правилам разрешения ресурсов. У вас будет только доступ к этой конкретной коллекции. Поиск ресурсов не будет пересекать область действия корня или приложения, если в запрашиваемом ключе не найден действительный объект. Тем не менее в некоторых случаях этот подход может иметь преимущество в производительности, поскольку область поиска ключа более ограничена. Более <xref:System.Windows.ResourceDictionary> подробную информацию о том, как работать со словарем ресурсов напрямую, можно узнать в классе.  
  
<a name="creating"></a>
## <a name="creating-resources-with-code"></a>Создание ресурсов с помощью кода  
 Пи создании приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] полностью в коде может также понадобиться создать в коде все ресурсы в этом приложении. Для достижения этой цели <xref:System.Windows.ResourceDictionary> создайте новый экземпляр, а затем добавьте <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>все ресурсы в словарь, используя последовательные вызовы. Затем используйте <xref:System.Windows.ResourceDictionary> созданный таким <xref:System.Windows.FrameworkElement.Resources%2A> образом элемент для установки элемента, <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>присутствуютй в области страницы, или . Можно также сохранить <xref:System.Windows.ResourceDictionary> как автономный объект, не добавляя его в элемент. Однако в этом случае для доступа к ресурсам внутри него потребуется ключ элемента, как для общего словаря. Свойство <xref:System.Windows.ResourceDictionary> элемента, не `Resources` прикрепленное к свойству элемента, не будет существовать как часть <xref:System.Windows.FrameworkElement.FindResource%2A> дерева элементов и не имеет области в последовательности поиска, которая может быть использована и связанными с ними методами.  
  
<a name="objectaskey"></a>
## <a name="using-objects-as-keys"></a>Использование объектов в качестве ключей  
 В большинстве случаев использования ресурса ключ ресурса устанавливается в виде строки. Однако различные функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] намеренно не используют строковый тип для указания ключей, вместо этого параметр является объектом. Возможность доступа объекта к ресурсу по ключу используется в поддержке стилей и тем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Стили в темах, которые становятся стилем по умолчанию для <xref:System.Type> нестилового управления, каждый из них включите элемент управления, к которому они должны применяться. Ввод с помощью ключа по типу обеспечивает надежный механизм поиска, который работает со стандартными экземплярами каждого типа элемента управления, а тип может быть обнаружен отражением и использоваться для создания стилей производных классов, даже если у производного типа нет стиля по умолчанию. Можно указать <xref:System.Type> ключ для ресурса, определяемого с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] помощью расширения [x:Type Markup.](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) Аналогичные расширения существуют для других случаев использования нестрокового ключа, поддерживающих функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как [Расширение разметки ComponentResourceKey](componentresourcekey-markup-extension.md).  
  
## <a name="see-also"></a>См. также раздел

- [Ресурсы XAML](xaml-resources.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
