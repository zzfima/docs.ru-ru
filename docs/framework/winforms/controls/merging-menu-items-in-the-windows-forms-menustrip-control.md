---
title: Слияние пунктов меню в элементе управления MenuStrip
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739050"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Слияние элементов меню в элементе управления MenuStrip в Windows Forms
При наличии приложения с многодокументным интерфейсом (MDI) можно объединить пункты меню или целые меню из дочерней формы в меню родительской формы.  
  
 В этом разделе описаны основные понятия, связанные с слиянием пунктов меню в приложении MDI.  
  
## <a name="general-concepts"></a>Общие понятия  
 В процедуру слияния входят как цель, так и система управления версиями:  
  
- Целевым элементом является <xref:System.Windows.Forms.MenuStrip> элемент управления основной родительской формы или родительского интерфейса MDI, в который объединяются пункты меню.  
  
- Источником является элемент управления <xref:System.Windows.Forms.MenuStrip> в дочерней форме MDI, содержащей пункты меню, которые необходимо объединить в целевое меню.  
  
 Свойство <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> определяет пункт меню, раскрывающийся список которого будет заполнен заголовками дочерних MDI-форм родительской формы MDI. Например, вы обычно перечислите дочерние элементы MDI, которые в данный момент открыты в меню **окно** .  
  
 Свойство <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> определяет, какие пункты меню берутся из <xref:System.Windows.Forms.MenuStrip> в дочерней форме MDI.  
  
 Элементы меню можно объединять вручную или автоматически. Элементы меню объединяются одинаково для обоих методов, но слияние активируется по-разному, как описано в разделах "слияние вручную" и "Автоматическое слияние" Далее в этом разделе. Как в ручном, так и в автоматическом слиянии каждое действие слияния влияет на следующее действие слияния.  
  
 <xref:System.Windows.Forms.MenuStrip> слияние перемещает пункты меню из одного <xref:System.Windows.Forms.ToolStrip> в другой, а не клонированы, как в случае с <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Значения Мержеактион  
 Действие слияния задается в элементах меню исходного <xref:System.Windows.Forms.MenuStrip> с помощью свойства <xref:System.Windows.Forms.MergeAction>.  
  
 В следующей таблице описывается значение и типичное использование доступных действий слияния.  
  
|Значение Мержеактион|Описание|Типичные случаи использования|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|Параметры Добавляет исходный элемент в конец коллекции целевого элемента.|Добавление пунктов меню в конец меню при активации некоторой части программы.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Добавляет исходный элемент в коллекцию целевого элемента в расположении, заданном свойством <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>, заданным для исходного элемента.|Добавление пунктов меню в середину или начало меню при активации некоторой части программы.<br /><br /> Если значение <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> одинаково для обоих пунктов меню, они добавляются в обратный порядок. Установите <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> соответствующим образом, чтобы сохранить исходный порядок.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Находит совпадение текста или использует значение <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>, если текстовое совпадение не найдено, а затем заменяет соответствующий пункт контекстного меню на пункт исходного меню.|Замена целевого пункта меню исходным пунктом меню с тем же именем, которое отличается от другого.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Находит совпадение текста или использует значение <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>, если текстовое совпадение не найдено, а затем добавляет все раскрывающиеся элементы из источника в целевой объект.|Создание структуры меню, которая вставляет или добавляет пункты меню в подменю или удаляет пункты меню из подменю. Например, можно добавить элемент меню из дочерней MDI-формы в главное меню <xref:System.Windows.Forms.MenuStrip>**Сохранить как** .<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> позволяет перемещаться по структуре меню без выполнения каких-либо действий. Он предоставляет способ вычисления последующих элементов.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Находит совпадение текста или использует <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> значение, если текстовое совпадение не найдено, а затем удаляет элемент из целевого объекта.|Удаление пункта меню из целевого <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Слияние вручную  
 Только <xref:System.Windows.Forms.MenuStrip>ные элементы управления участвуют в автоматическом слиянии. Чтобы объединить элементы других элементов управления, таких как <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.StatusStrip>, необходимо выполнить их слияние вручную, вызвав <xref:System.Windows.Forms.ToolStripManager.Merge%2A> и <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> методы в коде по мере необходимости.  
  
## <a name="automatic-merging"></a>Автоматическое слияние  
 Вы можете использовать автоматическое слияние для приложений MDI, активируя исходную форму. Чтобы использовать <xref:System.Windows.Forms.MenuStrip> в приложении MDI, задайте для свойства <xref:System.Windows.Forms.Form.MainMenuStrip%2A> целевой <xref:System.Windows.Forms.MenuStrip>, чтобы действия слияния, выполняемые в исходном <xref:System.Windows.Forms.MenuStrip>е, отражались в целевом <xref:System.Windows.Forms.MenuStrip>.  
  
 Вы можете активировать автоматическое слияние, активируя <xref:System.Windows.Forms.MenuStrip> в источнике MDI. После активации исходный <xref:System.Windows.Forms.MenuStrip> объединяется с объектом MDI. Когда новая форма становится активной, слияние возвращается в последнюю форму и активируется в новой форме. Это поведение можно контролировать, настроив свойство <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> по мере необходимости для каждого <xref:System.Windows.Forms.ToolStripItem>и установив свойство <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> для каждого <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [Элемент управления MenuStrip](menustrip-control-windows-forms.md)
- [Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Практическое руководство. Автоматическое слияние меню в приложениях MDI](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
